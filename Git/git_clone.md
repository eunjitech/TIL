# git clone(복제)

1. git 저장소에서 clone할 주소 가져오기
2. 로컬에서 가져온 주소 clone 하기

```bash
git clone https://github.com/eunjitech.git
```

3. 작업 후 순서대로 add, commit, remote, push

```bash
git init
git add .
git commit -am "Initial Commit"
git remote add origin https://...
git push -u origin master
```
