# Interactive Task Card 

A clean, high-fidelity, **fully interactive and stateful** single Todo Card component built for a modern productivity app.

## 🚀 What Changed from Stage 0

- Replaced modal-based editing with **inline edit mode** (the card itself transforms into an edit form)
- Added **Status Controls** with a dropdown (`data-testid="test-todo-status-control"`)
- Introduced **Priority Indicator** (colored dot) – `data-testid="test-todo-priority-indicator"`
- Added **Expand/Collapse** behavior for long descriptions with accessible toggle button
- Enhanced **Time Management**:
  - More granular relative time ("Due in 45 minutes", "Overdue by 1 hour")
  - Time stops updating when status is "Done" → shows "Completed"
  - Live overdue detection with prominent red indicator
- Status is now fully synchronized between:
  - Checkbox
  - Status dropdown
  - Visual status badge
- Improved visual feedback for "Done", "In Progress", "Pending", "High Priority", and "Overdue" states
- Significantly richer accessibility patterns

## ✨ Key Features

- All Stage 0 + new Stage 1 `data-testid` attributes for automated testing
- Fully editable inline form with title, description, priority, and due date
- Real-time status transitions (Pending → In Progress → Done)
- Collapsible description (auto-collapses if longer than ~110 characters)
- Dynamic overdue indicator with visual accent
- Live time updates every 30 seconds (`aria-live="polite"`)
- Smooth expand/collapse with proper ARIA attributes
- Fully responsive (mobile-first: 320px → tablet → desktop)
- Keyboard accessible navigation and interactions

## 🎨 New Design Decisions

- **Inline editing** instead of modal → feels more like a real app component (faster interaction, better context)
- Used a **colored priority dot** as the main priority indicator for quicker visual scanning
- Description is collapsed by default when long to keep the card compact and scannable
- Status dropdown placed prominently next to the visual badge for easy changes
- Overdue state uses strong red accent to draw immediate attention
- Maintained the warm, premium aesthetic while increasing information density

## ♿ Accessibility Notes

- All form fields in edit mode have proper `<label>` associations
- Expand/collapse toggle uses `aria-expanded` and `aria-controls`
- Time remaining updates use `aria-live="polite"`
- Full keyboard navigation support (Tab order: Checkbox → Status → Expand → Edit → Delete)
- Focus is managed when entering/exiting edit mode
- High contrast colors maintained across all states
- Touch targets enlarged for mobile users

## ⚠️ Known Limitations

- Only a single task card (as per requirements — not a full todo list)
- No persistence (data resets on page refresh)
- Edit mode does not include tags editing (kept simple as per spec)
- No focus trap implemented in edit mode (optional bonus)
- Time updates rely on `setInterval` (30s) rather than real-time second-by-second countdown

## Live Demo
[View Live Demo](https://task-todo-seven-phi.vercel.app)  

## How to Run Locally

1. Clone the repository:
   ```bash
   git clone https://github.com/Yhucee14/task-todo.git
   cd taskly-todo-card
