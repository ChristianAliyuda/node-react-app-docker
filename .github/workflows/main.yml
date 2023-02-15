name: Run the Action on each commit
on:
  push:
    branches-ignore: master
jobs:
  action-pull-request:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v2
        with:
          fetch-depth: 0
      - name: Run the Action
        if: startsWith(github.ref, 'refs/heads/feature')
        uses: devops-infra/action-pull-request@v0.5.5
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          title: ${{ github.event.commits[0].message }}
          assignee: ${{ github.actor }}
          label: automatic,feature
          template: .github/PULL_REQUEST_TEMPLATE/FEATURE.md
          old_string: "**Write you description here**"
          new_string: ${{ github.event.commits[0].message }}
          get_diff: true
