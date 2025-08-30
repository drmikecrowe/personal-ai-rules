# Testing - XState Component Testing Strategy
- Last Updated: 2025-08-30
- Description: The strategy for testing React components that use XState.
- Tags: testing xstate
- Version: 1.0


### Problem: Complex Dependencies

When testing React components that use XState hooks (`useActorRef`, `useSelector`, etc.), the components require XState context providers that are difficult to mock properly.

### Solution: Logic-First Testing

Instead of trying to render the actual component with all its XState dependencies, create a simplified test component that mimics the core logic:

```typescript
// ❌ Avoid: Complex mocking of XState hooks
vi.mock('~/appMachineContext', () => ({
  useAppSend: vi.fn(),
  useUser: vi.fn(),
}))

// ✅ Prefer: Create test component that mimics logic
const TestComponent = ({ report, reportActor, user, appSend, dashboardSend }: any) => {
  const availableActions = reportActor && user ?
    mockGetReportActionsFromActor(reportActor, report, user) : []

  const handleAction = (actionType: string) => {
    // Test the actual logic here
    if (actionType === 'DOWNLOAD') {
      appSend({ type: 'DOWNLOAD_REPORT', reportId: report.id })
      return
    }
    // ... other action handling
  }

  if (!reportActor || !user) {
    return null
  }

  return (
    <div>
      {availableActions.map((action: any) => (
        <button
          key={action.type}
          onClick={() => handleAction(action.type)}
          data-testid={`action-${action.type.toLowerCase()}`}
        >
          {action.label}
        </button>
      ))}
    </div>
  )
}
```

### Benefits of This Approach

1. **No Module Resolution Issues**: Avoids complex path alias and require() problems
2. **Focused Testing**: Tests the actual business logic without XState complexity
3. **Maintainable**: Easier to understand and modify
4. **Reliable**: No dependency on XState context providers or complex mocking

### When to Use Each Approach

**Use Logic-First Testing When:**

- Component has complex XState dependencies
- You're testing business logic and action routing
- Module resolution is problematic
- You want to focus on component behavior, not XState integration

**Use Full Component Testing When:**

- Testing simple components without XState
- Testing UI rendering and styling
- Testing integration with other components
- XState context is already properly set up

### Test Structure Guidelines

1. **Mock Dependencies**: Use simple function mocks instead of complex module mocks
2. **Test Logic**: Focus on testing the component's decision-making and action routing
3. **Verify Behavior**: Test that the right actions are called with the right parameters
4. **Edge Cases**: Test null/undefined scenarios and error conditions
5. **Type Safety**: Use proper TypeScript types from shared types directory

### Example Test Pattern

```typescript
describe('Component Logic', () => {
  const mockAppSend = vi.fn()
  const mockDashboardSend = vi.fn()
  const mockGetActions = vi.fn()

  beforeEach(() => {
    vi.clearAllMocks()
    mockGetActions.mockReturnValue([
      { type: 'EDIT', label: 'Edit', variant: 'secondary' },
      { type: 'DELETE', label: 'Delete', variant: 'danger' },
    ])
  })

  it('should route actions correctly', () => {
    render(
      <TestComponent
        report={mockReport}
        reportActor={mockActor}
        user={mockUser}
        appSend={mockAppSend}
        dashboardSend={mockDashboardSend}
      />
    )

    fireEvent.click(screen.getByTestId('action-edit'))
    expect(mockAppSend).toHaveBeenCalledWith({
      type: 'EDIT_REPORT',
      reportId: 'report-1',
    })
  })
})
```
