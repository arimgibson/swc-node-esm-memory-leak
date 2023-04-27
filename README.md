### swc-node ESM Memory Leak

Fedora 38
Kernel: Linux 6.2.11-300.fc38.x86_64
Node v20.0.0

Only occurs with ESM, likely due to the breaking changes introduced in Node v20

https://nodejs.org/en/blog/release/v20.0.0
> Custom ESM loader hooks run on dedicated thread
> ESM hooks supplied via loaders (--experimental-loader=foo.mjs) now run in a dedicated thread, isolated from the main thread. This provides a separate scope for loaders > and ensures no cross-contamination between loaders and application code.

Credit to [@Jack-Works](https://github.com/Jack-Works) for mentioning breaking change in [ts-node #1997](https://github.com/TypeStrong/ts-node/issues/1997#issuecomment-1517388341)