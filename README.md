# Stacking Co-operative Resource Claiming (scrc)

**scrc** is a protocol that allows various computers to share a common resource.

The protocol is based on a continuous cycle of:
  - CLAIM
  - CHECK
  - EXECUTE
  - RELEASE

Claiming is done by adding a unique identifier of the client onto a stack.
The client then regularly checks to see if its ID has reached the top of the stack, indicating that it is in control.
Once in control the client will communicate with the resource and execute its tasks.
When the tasks are completed the client removes its ID from the stack.
The resource(-server) or one of clients runs the stackmaster script periodically. This removes any invalid IDs and keeps the stack clean.

The easiest "unique identifier" is the IP-address of the client. This also assures an easy way for the stackmaster to check if a client is still alive.
