---
layout: post
title:  "Git Config"
date:   2019-04-10 13:00:00 +0800
categories: tutorials
---
## Settings to use different emails
In `.gitconfig`
```
[includeIf "gitdir:~/"]
	path = .gitconfig-personal
[includeIf "gitdir:~/work/"]
	path = .gitconfig-work
```
In `.gitconfig-personal`
```
[user]
	user = <name>
	email = <email>
```

### Reference
- [Different git identities](https://www.codexpedia.com/devops/includeif-for-creating-different-git-identities/)
