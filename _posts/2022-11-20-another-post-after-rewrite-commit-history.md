---
layout: post
title:  "Post with iPad"
date:   2022-11-20 22:42:36 +0800
categories: blog
---
```
git filter-branch -f --env-filter '
OLD_EMAIL="old-email@example.com"
CORRECT_NAME="your correct name"
CORRECT_EMAIL="your-correct-email@example.com"
if [ "$GIT_COMMITTER_EMAIL" = "$OLD_EMAIL" ]
then
    export GIT_COMMITTER_NAME="$CORRECT_NAME"
    export GIT_COMMITTER_EMAIL="$CORRECT_EMAIL"
fi
if [ "$GIT_AUTHOR_EMAIL" = "$OLD_EMAIL" ]
then
    export GIT_AUTHOR_NAME="$CORRECT_NAME"
    export GIT_AUTHOR_EMAIL="$CORRECT_EMAIL"
fi
' --tag-name-filter cat -- --branches
```
作者：Marshall3572
链接：https://www.jianshu.com/p/66942cdf77e6
來源：简书
简书著作权归作者所有，任何形式的转载都请联系作者获得授权并注明出处。