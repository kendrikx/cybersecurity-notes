# Linux Users, Groups and Permissions - My Learning Notes

## Commands Learned
- `sudo` — Run commands with elevated (superuser) privileges
- `su` — Switch to another user account
- `chmod` — Modify file and directory permissions
- `chown` — Change file and directory ownership

---

## Users and Groups
- Created new user accounts
- Understood primary and secondary groups
- Explored user information (`id`, `/etc/passwd`, `/etc/group`)
- Created new groups
- Added users to groups

---

## Sudo Privileges

**Why sudo access is important:**
- Enhances security by limiting direct root usage
- Provides accountability through command logging
- Allows controlled and temporary elevated access
- Prevents accidental system damage from constant root login

---

## File Permissions

### Common Permission Examples
- **777** — Everyone has full read, write, and execute access (insecure)
- **755** — Owner has full access, others can read and execute
- **644** — Owner can read and write, others can only read
- **600** — Owner has full access, private to owner only

---

## File Ownership
- `chown` changes ownership of files and directories

## Permission Modification
- `chmod` changes file and directory permissions

---

## Reflection

### What I Understood Well
- Users and groups management
- Basic `sudo` usage
- File permissions (rwx)
- Ownership concepts

### What Needs More Practice
- Advanced `chmod` mastery
- Group management
- Permission combinations

---

**Progress**  
- Completed multiple Linux administration labs on LabEx  
- **Skill Progress**: 28/118

---

**Last Updated**: May 14, 2026  
**Status**: In Progress