git revert <commit-hash>
    Create a completely new commit that introduces the exact opposite changes of the 
    specified bad commit. Safest way to undo changes already pushed to production.

git reset --soft <commit-hash>
    Move your branch pointer backward in time, but keep your changes staged in the index.

git reset --hard <commit-hash>
    CRITICAL WARNING: Move your branch pointer backward and COMPLETELY wipe out all local 
    working directory changes to match that commit. Uncommitted work will be permanently lost.

git reflog
    The ultimate safety net. Records every movement of HEAD (commits, checkouts, resets). 
    Use this to recover "lost" commits or broken resets.

git bisect start / git bisect bad / git bisect good
    Use binary search to find the exact commit that introduced a bug or broke a pipeline build.

--------------------------------------------------------------------------------
6. DEVOPS INTEGRATION SUMMARY
--------------------------------------------------------------------------------
In DevOps, Git isn't just for code storage; it acts as an automated workflow engine:
1. Webhooks: Git repositories trigger CI/CD pipelines (Jenkins, GitHub Actions, GitLab CI) 
   automatically on 'git push' or Pull Request creation.
2. GitOps: Tools like ArgoCD or Flux continuously monitor Git repositories containing 
   Kubernetes declarations and automatically reconcile the cluster state to match Git.
3. Pull/Merge Requests: Code review gates where automated tests, vulnerability scanners, 
   and peer approvals must pass before code can reach production.
================================================================================
