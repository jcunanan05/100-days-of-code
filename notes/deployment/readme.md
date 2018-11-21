# Deployment

This is my notes by exploring deployment.

## What is CI?

res: [https://docs.travis-ci.com/user/for-beginners/](https://docs.travis-ci.com/user/for-beginners/)

Merging small code changes frequently, in the opposite of building the whole codebase first and deploying. It also has auto-building and testing code changes.

### Common words

- job - automated processes that runs in phases _e.g. (testing, compiling your code)_
- phase - steps _e.g. install phase, script phase, deploy phase_
- build - group of jobs. when a build finishes, jobs are finished.
- stage - group of jobs that run in parallel

### Environment / Infrastructures

- Container-based - default environment, Linux Ubuntu environment, faster to startup, less resources and doesn't support sudo
- Sudo-enabled - Linux Ubuntu environment, full virtual-machine environment, starts slower than containers, more resources, and supports `sudo`
- OSX - uses OSX OS, useful for building projects that require OSX (Swift)

## Connecting a Domain name on a VPS

I recently experienced first time on how to connect a Go Daddy domain on a VPS container, AWS Lightsail.

1. Go to GoDaddy Dashboard > DNS Management
2. Look for the root DNS document called `@`
3. `@` means root, then put a static IP there. The static IP will be found on your AWS Lightsail Instance.
