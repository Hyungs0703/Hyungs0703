
<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Hyungs0703&layout=compact&theme=tokyonight"><br><br>
<img src="https://github-readme-stats.vercel.app/api?username=Hyungs0703&show_icons=true&theme=tokyonight">

name: GitHub-Profile-3D-Contrib

on:
  schedule: # 03:00 JST == 18:00 UTC
    - cron: "0 18 * * *"
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    name: generate-github-profile-3d-contrib
    steps:
      - uses: actions/checkout@v2
      - uses: yoshi389111/github-profile-3d-contrib@0.6.0
        env:
          GITHUB_TOKEN: ${{ secrets.TOKEN }}
          USERNAME: ${{ github.repository_owner }}
      - name: Commit & Push
        run: |
          git config user.Hyungs0703 github-actions
          git config user.[email](https://github.com/Hyungs0703) github-actions@github.com
          git add -A .
          git commit -m "generated"
          git push
