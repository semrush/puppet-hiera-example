### What is it
This project is meant to present how can be Puppet improved with Hiera. The project was created by team of system administrators at SEMrush for demonstration purpose only and is not full working example that can be used without changes.

### Project description
The project consists of several direcroties including:
- `profiles`
- `hiera`

Directory `profiles` has three profiles for Puppet, which can be used to be an entry points for modules:
- `docker.pp` prepares docker module and can install linux kernels if it's needed
- `db/postgresql.pp` is an entry point for postgresql module and lets to configure module with more precision
- `db/redis.pp` shows how to work around an khown issue with redis and sysctl vm.overcommit_memory parameter using profiles

Directory `hiera` consists of configuration files for project named `kicker`. This is a fictitious project that shows how hierarchy in hiera works and can be used.
This example describes following environment:
- We have 2 db-servers running PostgreSQL
- 2 servers have role `frontend` and run nginx
- 2 more servers are app servers and run docker with some application

Besides we have production stage and development stage. They are identical except for some configuration moments.

Look at `hierarchy` file to understand in which order are searched files.

### Summary
The example shows how:
- Basing on facts is builded hierarchy
- Basing on hierarchy values in yaml files are overrided
- To make configuration code reusable
- To create an architecture of a project
- To use hiera for configuring servers

### More info
Here is an [article](https://habr.com/company/semrush/blog/412587/) on habr.com (in Russian) that fully describes this hierarchy structure
