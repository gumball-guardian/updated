# updated

updated is meant to be an automatic binary update service for meshd and other components (including updated)

updated requires all binaries to be signed by the configured CA (how do we sign ELF binaries, spike)?

updated does health checks on meshd and other updated components, and reverts updates that don't eventually report ready, to last known good.  It may then try to retry the update a couple times and then give up and wait for the next update.

Based on a configured schedule, updates should be rapidly applied to quickly evolve the system.  You should always be able to pin a partiuclar version which updates to that configured version and then does not apply any future updates while the pin is in place.
