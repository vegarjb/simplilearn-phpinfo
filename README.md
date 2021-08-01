# simplilearn-phpinfo

```
GITHUB_USERNAME=academiaonline
GITHUB_PROJECT=simplilearn-phpinfo
GITHUB_BRANCH=2021-08

git clone https://github.com/${GITHUB_USERNAME}/${GITHUB_PROJECT}
cd ${GITHUB_PROJECT}
git checkout ${GITHUB_BRANCH}

docker image build --file Dockerfile-single-line --tag ${GITHUB_USERNAME}/${GITHUB_PROJECT}:single ./
docker container run --detach --entrypoint /usr/bin/php --name ${GITHUB_PROJECT}_single --read-only --rm --user nobody --volume ${PWD}/src:/src:ro --workdir /src ${GITHUB_USERNAME}/${GITHUB_PROJECT}:single -f index.php -S 0.0.0.0:8080
```
