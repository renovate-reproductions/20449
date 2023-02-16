# renovate-force-push

## Steps to reproduce

1. Clone the repo, it has a failing GitHub Actions workflow
2. Push the repo, wait a bit for the GitHub Action to fail
3. In the repository settings add "test" (the actions workflow name) to required status checks for the `main` branch before merge, so Renovate could automerge (see screenshot)

<img alt="Screenshot 2023-02-16 at 09 56 52" width="828" src="https://user-images.githubusercontent.com/298166/219316575-a226abb4-d6d7-4975-b4c2-8caf2d38e98f.png">

4. Run Renovate, it will create a branch called `renovate/actions-exec-1.x`
5. Re-run Renovate, the status check fails and it creates a PR
6. In the PR, check "Retry/Rebase"
7. Run Renovate multiple times, the checkbox is not cleared and it keeps force pushing

