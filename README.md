## Building a CI/CD pipeline using github actions
![TarunKamur_calculator-app-in-react_ Real World calculator functionalities gained by using pure React JS  - Google Chrome 03-02-2024 17_03_48](https://github.com/TarunKamur/Geniehub-Devops/assets/152691126/681b4dfd-329f-4e9e-8692-d17858643315)


## First of all go github repository and then go in .github and make workflows directory and inside that directory make a name .yml file
![image](https://github.com/TarunKamur/Geniehub-Devops/assets/152691126/432af484-0621-4ea6-9e80-88fe300af1a8)



## or else you can also go to actions and create a new workflow github will automatically make you a .yml file where you can write your code
![Editing Geniehub-Devops_README md at main · TarunKamur_Geniehub-Devops - Google Chrome 03-02-2024 17_19_44](https://github.com/TarunKamur/Geniehub-Devops/assets/152691126/4673d6d6-da5a-40e1-aac3-f6a2c0cd6d3d)

## then write your CI/CD code in your .yml file 

```
name: calculator-app-in-react
on:
  push:
    branches:
      - main  # Adjust branch name as needed
  workflow_dispatch:
jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout Repository
      uses: actions/checkout@v2

    - name: Set up Node.js
      uses: actions/setup-node@v2
      with:
        node-version: 16

    - name: Install Dependencies
      run: npm install

    - name: Build React App
      run: npm run build

  deploy:
    runs-on: ubuntu-latest
    needs: build
    steps:
    - name: Deploy to GitHub Pages
      uses: JamesIves/github-pages-deploy-action@releases/v3
      with:
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
        BRANCH: gh-pages
        FOLDER: public  # The folder where the build artifacts are located
```

## then commit changes, code will changes according to workflow and package.jshon .

## the changes will appear in actions.
![image](https://github.com/TarunKamur/Geniehub-Devops/assets/152691126/a0f49ee7-2f75-4e24-9f31-1fff08421adb)

# also to deploy your application you will have to go to pages and then choose deploy from branch and choose branch as gh-pages and then save


#then you have to go to package.json and have to paste your url as homepage there

```
"homepage" : "your_url"
"Homepage (Web brower):https://tarunkamur.github.io/calculator-app-in-react/"


## now you CI/CD pipeline using github actions has been built successfully and when you push anything it will automatically go through the stages and deployed successfully.

## After Clicking the git-url
![image](https://github.com/TarunKamur/Geniehub-Devops/assets/152691126/5654c692-b7b1-4b5d-abf8-90ce1af17061)
![image](https://github.com/TarunKamur/Geniehub-Devops/assets/152691126/6558ce1a-a767-46c5-a6a5-c887b06cf80c)



## like i have updated package.json automatically it has gone through process
