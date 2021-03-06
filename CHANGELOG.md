# 0.4.0 (December 14, 2015)

IMPROVEMENTS

* [GH-5] Tasks are now cancellable.  When scheduling a task via e.g. `scheduler.scheduleOnce()`, the returned
  [Cancellable](http://doc.akka.io/api/akka/2.3.9/index.html#akka.actor.Cancellable) can now be cancelled;
  if it is cancelled before its execution time, then the `MockScheduler` will not run the task.
  (thanks mmacfadden)


# 0.3.1 (August 05, 2015)

BUG FIXES

* [GH-4] Fix deadlock involving `MockScheduler#schedule()` and `VirtualTime#advance()`. (thanks emrecelikten)


# 0.3.0 (March 23, 2015)

BREAKING CHANGES / BUG FIXES

* [GH-1] Tasks scheduled to run at the same time will be run in registration order.
  This is primarily a bug fix to ensure that "conflicting" tasks are run in a well-defined, deterministic order.
  The breaking change is that unlike the previous version we will not run one-time tasks always before recurring tasks.
  If there is a scheduling "conflict", then the tasks -- whether one-time or recurring -- will always be run in the
  order of registration with the scheduler. (thanks DylanArnold)


# 0.2.0 (January 23, 2015)

* Initial release
