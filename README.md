# Laravel Render.com deploy template
Original readme here = https://github.com/codingnninja/laravel-render-template\

With few adjustments to reduce build time which very critical to Free Instances users, by :
1. Including node_modules into the Docker Image\

When we're using Free Instances on render.com, which will be go to inactive state after 15 minutes of inactivity, it's very critical to reduce needed time to "wake up" the server when we're wanted our web
back online again ASAP.\
In my test, npm install and npm run build causing spinning back the server took way longer than expected. So best usage for Free Instance users :\
1. In your local development environment, run npm install and npm run build first\
2. After that, delete node_modules from your .gitignore files so that node_modules folder will also getting pushed to the GitHub repository since we're utilizing GitHub for render.com\
3. So every time the server spinning back, it won't require longer time to boot up the server again since we didn't execute npm install and npm run build anymore.
