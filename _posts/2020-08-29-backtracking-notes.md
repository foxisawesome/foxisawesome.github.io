---
layout: post
title: Backtracking Notes
date: 2020-08-29 22:38 -0400
categories: note
---

# Backtracking

**Template**:
```python
def bt(path, choice_list):
    if (stopping condition):
        output.append(path[:])
        return 

    for i in choice_list:
        if not isValid():
            continue # isvalid is to prune the tree.

        path.append()
        bt(path, (choice_list - path))
        path.pop()
```

Note:

- Time Complexity O(N!)
- in `output.append(path[:])`, need deep copy. hence `path[:]`. 
- reference 1: [labuladong](https://labuladong.gitbook.io/algo/di-ling-zhang-bi-du-xi-lie/hui-su-suan-fa-xiang-jie-xiu-ding-ban) \
- reference 2: [负雪明烛](https://blog.csdn.net/fuxuemingzhu/article/details/101900729?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522159727800419724846433388%2522%252C%2522scm%2522%253A%252220140713.130102334.pc%255Fblog.%2522%257D&request_id=159727800419724846433388&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~blog~first_rank_v2~rank_blog_default-1-101900729.pc_v2_rank_blog_default&utm_term=%E5%9B%9E%E6%BA%AF%E6%B3%95&spm=1018.2118.3001.4187)