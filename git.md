# Git

## Different git projects with individual ssh keys
1. Create ssh key.
2. Add public ssh key to your Github/Gitlab profile.
3. Add an ssh config file (`~/.ssh/config`) to map ssh key to a git account
```bash
Host git-work
   HostName git.dunder.mifflin.com
   User git
   IdentityFile ~/.ssh/id_work
 Host git-private
   HostName github.com
   User git
   IdentityFile ~/.ssh/id_private
Host git-secret
  HostName git.white.rabbit.com
  User git
  IdentityFile ~/.ssh/id_rabbit
```
4. Use specified host handle when checking out repo, e.g. `git clone git@git-private:dwight-schrute/beet-farm.git`


If you already have checked out a repo and want to start using the correct ssh key from the config, you can use
- `git remote set-url origin git@git-private:dwight-schrute/beet-farm.git`
