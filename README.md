# SlowGitSSH

Git has name resolution issues under some versions. This is a great fix.

Some versions of git, in conjunction with some ISP DNS configurations, seem to have trouble.
The git client, when cloning, pushing, or pulling, will take around 2 minutes to timeout before trying a normal DNS resolution.

To bypass this issue, you can tell SSH to connect using normal DNS up front.
To do this, you put an entry in your .ssh/config file with the git server (origin)'s Host, and tell it to use inet to look it up first.

Included in this repository is an example of this config file with gitlab.com and github.com entries already in place.
This could be extended to Bitbucket, other servers, or your own hosted git server if you're seeing this problem.

---

Instructions:

- Find your ssh client's configuration directory. In Linux by default, this is $HOME/.ssh/
- Copy the example 'config' file into that directory, or append it to your exisiting config file
- Optional: add a Host entry for a different git server if you're using one
- Test your git clone/push/pull commands
- Breath a sigh of relief now that you've patched things against your ISP's bad DNS setup (see: Comcast's DNS kluge)

---

Author: Aaron S. Crandall \<acrandal@gmail.com>
Copyright: 2024 - Use it as you will / public domain license
