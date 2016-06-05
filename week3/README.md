# VPC Cloudformation

AKA The Black Hole that will suck you into an infinite spiral of darkness and destruction

## Network Structure & Dependencies

    /-------------------------------------------------------------------------|
    |
    |                      ======== IGW ========
    |          /------------> ∆   ∆         ∆ <------------\
    |         /              /     \         \              \
    |        /   === test === <-----\         === prd === <--\
    |       /          |             |             |           \
    |     === dev ===  |  === tst ===              |  === prd ===
    |         |        |       |                   |       |
    |         |        |       |                   |       |
    |     ======================= infrastructure =======================
    |
    \-------------------------------------------------------------------------|

*   create VPC

*   create private subnets

*   create public subnets

*   create IGW

*   create IGW routes

    *   int-prd -> ext-prd
    *   int-tst -> ext-tst
    *   infrastructure <-> \*
