# Tran Quoc Khanh Blog

This project uses Jekyll framework. For more detail, please visit [https://jekyllrb.com](https://jekyllrb.com/)

## How to test new post?
0. Run ```bundle install``` (the first time)
1. Run ```bundle exec jekyll serve```
2. Go to address: `localhost:4000`

## How to publish new post?
1. Run ```jekyll build``` or ```bundle exec jekyll build```
2. Commit ```git add . && git commit -m "Update posts"```
3. Push ```_site``` folder to deploy remote: ```git subtree push --prefix _site deploy master```