# Test Peer Dependencies

This tests shows a way to handle peer dependencies.

Upon observation of behaviors of `npm install` and `npm prune` we found that, in the case that some package peerDepends __AND__ devDepends on another package, upon running `npm prune --production`, the peerDepending package is not removed.

One would expect it to be removed since it is a devDependency, but somehow it is getting excluded due to existing as peerDependecy.

This is not a big deal in general. But a great discovery for building packages that require their peerDependencies for testing purposes or for usage in bundled demos that use dependencies from `node_modules`.
