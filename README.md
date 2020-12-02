# The Best Work Order System in The World

### Diagrams:
* [Work Order Completed](/../../raw/main/diagrams/output/WorkOrderCompletedFlow.svg)
* [Work Order Stopped](/../../raw/main/diagrams/output/WorkOrderStoppedFlow.svg)

### Assumptions:
* There are two types of operators: normal and supervisor.
* Operators can create work orders in the Work Order API.
* For every change in the status of a work order, there will be a notification from the Notification API.
* An operator can only change the status of a work order to "started" when no one else has taken it.
* If an operator attempts to mark a work order "started" when it has already been taken, the request must be cancelled and the requester informed.
* Only the owner of the work order can change the status to "completed" when the current status is "started".
* The work order owner and supervisor can stop the work order when the status is "started".
* If the work order is "started" after 30 seconds, it should be changed to the previous state.
