

## About me

![Typing SVG](https://readme-typing-svg.herokuapp.com?font=Fira+Code&pause=1000&color=F78A20&width=435&lines=Hi+there!+I'm+Hilary;I+love+building+cool+things)

👀 I’m interested in : WebDevelopment && MobileApplications

🌱 I’m currently learning: Golang || JavaScript || Rust

💞️ I’m looking to collaborate on : OpenSource Projects
<table>
  <tr>
    <td>
      <a href="https://github.com/Hilary505/github-readme-stats">
        <img height="300" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Hilary505&layout=pie" />
      </a>
    </td>
    <td width="30"></td> <!-- space between -->
    <td>
      <img height="300" src="https://github-readme-stats.vercel.app/api?username=Hilary505&show_icons=true&theme=radical" />
    </td>
  </tr>
</table>
name: generate animation

on:
  # run automatically every 24 hours
  schedule:
    - cron: "0 */24 * * *" 
  
  # allows to manually run the job at any time
  workflow_dispatch:
  
  # run on every push on the master branch
  push:
    branches:
    - master
    
  

jobs:
  generate:
    permissions: 
      contents: write
    runs-on: ubuntu-latest
    timeout-minutes: 5
    
    steps:
      # generates a snake game from a github user (<github_user_name>) contributions graph, output a svg animation at <svg_out_path>
      - name: generate github-contribution-grid-snake.svg
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
          
          
      # push the content of <build_dir> to a branch
      # the content will be available at https://raw.githubusercontent.com/<github_user>/<repository>/<target_branch>/<file> , or as github page
      - name: push github-contribution-grid-snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
😄 Pronouns: he/him
<!---
Hilary505/Hilary505 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
