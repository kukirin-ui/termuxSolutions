# OnePlus 15: does oplusreserve1 exist on global builds?

XDA post: https://xdaforums.com/posts/90778624/

Yeah. Global/EU/IN OnePlus 15 units have oplusreserve1 too.

It is not a China-only partition. koaaN has tried taking an oplusreserve1 image from a global/EU/IN phone and flashing it onto a CN one; it exists on those retail units, it just will not boot someone else's device because the data inside is device-unique:
https://xdaforums.com/t/ideas-to-keep-fastboot-access-before-relocking-cn-variant.4777622/

On CN ColorOS that's where Deep Testing keeps the unlock state, which is why it matters there. On global you unlock with normal fastboot, but the partition is still in the table.

To confirm on your own phone (root or recovery shell):

ls -l /dev/block/by-name/oplusreserve1

Some builds put it under /dev/block/bootdevice/by-name/ instead. Do not flash another unit's dump onto yours.
