# Use of Hybrid Approach mediator orchestration

## Status
Accepted

## Context 

Farmacy foods is at an early stage of its evolution and expansion/pivoting is expected.
Loose coupling with the current 3rd party systems is desirable.

## Decision

We have chosen to use an event mediator based architecture to choreograph different systems(chefTech,accounting,order history) when and order is successfully placed.
We have chosen spring integration to implement the mediator since we are already familiar with spring ecosystem and this helps us to existing libraries in the ecosystem (eg auth)

We also opted for a BFF to orchestrate between core domain services.
This is because we do not want to put too much domain logic (eg association of coupons/products) in the mediator.
Also this logic is likely to change at a quick pace.

## Consequences

In near term implementing both patterns will take more time and effort .
The extra work for creating bffs and event listeners etc will be planned for.