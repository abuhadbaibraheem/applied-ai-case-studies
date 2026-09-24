# Restaurant voice ordering

**Context:** [OrderTech](https://ordertech.ai) · Voice AI · Restaurant operations

## The problem

A restaurant order is more than a transcript. Callers change their minds, interrupt, use informal item names, and leave out required options. Menus, availability, and prices can change. An assistant has to turn the conversation into a valid order without inventing menu items or silently submitting the wrong cart.

## My work

I have worked on the voice ordering flow and the hand-off between conversation logic, backend services, and restaurant operations. The useful engineering question is: how do we preserve what the customer meant while keeping the final order consistent with the live menu?

## Design approach

1. **Ground the conversation in menu data.** Use structured menu and option data when resolving items, modifiers, and prices.
2. **Keep an explicit cart state.** Track quantities, changes, removals, and required choices across turns rather than reconstructing the order from the last message.
3. **Validate before submission.** Check that selected items and options form a valid order, and ask for missing details.
4. **Confirm the final order.** Present the cart back to the customer before creating it.
5. **Plan for recovery.** Handle interruptions, misunderstood items, unavailable choices, and transfer or fallback when the assistant cannot finish confidently.

## Validation focus

I review realistic conversations: corrections halfway through an order, multiple similar menu items, modifier changes, cancellations, and incomplete choices. I also check the operational hand-off, latency, and failure paths. This case study describes the approach; it does not publish private implementation details or claim a measured production result.

[OrderTech website](https://ordertech.ai) · [Back to case studies](../README.md)
