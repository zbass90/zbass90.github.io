---
title: "[Blog] Jekyll의 Chirpy Theme 깃 블로그 만들기"
date: 2022-01-04 +0800
categories: [Blog]
tags: [blogging, chirpy, jekyll]
---

이 글의 베이스는 Chipy 공식 홈페이지의 [**Getting Started**](https://chirpy.cotes.page/posts/getting-started/)글이며 자세한 내용은 해당 사이트에서 확인 가능합니다.<br>
[**재우님의 블로그**](https://joojaewoo.github.io/posts/startBlog/)를 참고해서 빌드와 포스팅했습니다.

### Installation

1. 깃허브에서 [Chirpy Repo](https://github.com/cotes2020/jekyll-theme-chirpy)에서 포크로 담은 Repository Name을 `{GithubUserName}.github.io`로 변경합니다.

2. 터미널을 켜고 Repository를 localhost로 가져옵니다.

   원하는 위치로 이동하여 아래 명령어를 실행!<br>
   `$ git clone https://github.com/USERNAME/USERNAME.github.io.git -b master --single-branch`

### Setting up the local environment

로컬에서 블로그를 운영하려면 몇가지 설치가 필요합니다.<br>
[Jekyll 설치 가이드](https://jekyllrb.com/docs/installation/)를 참고해서 운영체제에 맞게 다운 받아주시면 됩니다.

```bash
$ ruby -v
$ gem -v
$ gcc -v  ## g++ -v, make -v
```

Ruby, gem, gcc 버전 체크 후 이상이 없다면 다음을 진행하면 됩니다.<br>
블로그 디렉토리로 이동한 후 `$ bundle install` 명령을 실행하면 모두 자동으로 설치됩니다.
혹시 위 명령어에서 ``` can`t find bundler ```와 같은 에러가 발생하였다면 

- Update RubyGems: <br>`$ gem update --system` 
- Install the exact Bundler: <br>`$ gem install bundler -v "$(grep -A 1 "BUNDLED WITH" Gemfile.lock | tail -n 1)"` <br>
RubyGem을 업데이트 하시거나 명령어로 설치하시면 됩니다.


### Usage

#### Initialization

이제 프로젝트 폴더로 이동하여 아래 명령어를 통해 Initialization을 진행합니다.<br>
`$ bash tools/init.sh`

> Note: 깃허브 페이지에 배포하는 것을 원치않는다면 위 명렁어 뒤에 `--no-gh`옵션을 붙여 실행하면 됩니다.
위 명령어를 실행하면 아래와 같은 작업들이 수행되어집니다.

1. 특정 파일과 폴더를 삭제합니다.
   - `.travis.yml`
   - `_posts` 폴더 속 파일들
   - `docs` 폴더
2. `--no-gh`옵션을 붙여주었다면 `.github`폴더가 삭제됩니다. 그렇지 않다면, `.github/workflows/pages-deploy.yml.hook`의 `.hook`확장자 파일을 삭제함으로써 Github Action workflow를 셋업이 가능합니다. 그 후에 `.github`폴더의 다른 파일, 폴더들을 삭제하면 됩니다.
3. 자동으로 commit을 생성합니다.

### Configuration

`_config.yml`파일로 가서 여러가지 설정값을 변경해야 하며 아래는 대표적인 설정값입니다. `_config.yml`파일에서 아래에 해당하는 값들을 변경하면 됩니다.

- `url`: 블로그의 주소를 입력해주세요.<br>
  e.g. `url: 'https://zbass90.github.io'`
- `avatar`: 대표하고 싶은 이미지 파일을 넣어주세요. 일반적으로 이미지 파일은 `/assets/img/`폴더에 넣고 불러서 사용합니다.<br>
  e.g. `avatar: /assets/img/sample.png`
- `timezone`: [Find your timezone](http://www.timezoneconverter.com/cgi-bin/findzone/findzone)에서 자신이 속한 지역을 찾아 넣어주세요.<br>
  e.g. `timezone: Asia/Seoul`
- `theme_mode`: 블로그의 테마모드를 설정해주는 값으로, 다크와 라이트중 선택할 수 있습니다.<br>
  e.g. `theme_mode: dark` ... `저는 dark가 좋아용.`

### Run Locally

포스팅을 배포하기전에 내 로컬에서 포스팅 혹은 변경사항이 제대로 적용되었는지 아래 명령어를 통해 바로 확인 가능합니다.

`$ bundle exec jekyll s`

위 명령어를 실행하고 [localhost:4000](http://localhost:4000)으로 접속이 가능합니다.

### Deploy on Github Pages

1. 아무 변경사항을 `origin/master` 푸시해주어 Github Actions workflow를 발동?(trigger) 시킨다. 빌드가 제대로 완료되었다면 레포의 브랜치에 `gh-pages`브랜치가 생성된것을 확인할 수 있을것이다.
2. 레포의 `setting`으로 들어가서 아래로 쭈욱 내리면 Github Pages에 대한 설정이 나온다.  **Branch**를 `gh-pages`로 변경해준뒤 `save`를 클릭해주자.


### End 
`_post/`폴더에서 markdown파일을 작성 -> Github.에 Push -> 블로그에 포스팅 완료! 이상입니다.

