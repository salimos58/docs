---
title: 审查拉取请求中的建议更改
intro: 在拉取请求中，您可以审查和讨论提交、更改的文件以及基本和比较分支中文件之间的区别（或“差异”）。
redirect_from:
  - /github/collaborating-with-issues-and-pull-requests/reviewing-changes-in-pull-requests/reviewing-proposed-changes-in-a-pull-request
  - /articles/reviewing-proposed-changes-in-a-pull-request
  - /github/collaborating-with-issues-and-pull-requests/reviewing-proposed-changes-in-a-pull-request
  - /github/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/reviewing-proposed-changes-in-a-pull-request
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
topics:
  - Pull requests
shortTitle: 审核建议的更改
---

## 关于审查拉取请求

您可以在拉取请求中每次审查一个文件的更改。 在拉取请求中审查文件时，可以对特定更改留下单个注释。 在完成审查每个文件后，您可以将该文件标记为已查看。 这会折叠文件，帮助您识别还需要审查的文件。 拉取请求标题中的进度条显示您查看过的文件数。 在按需要审查文件后， 您可以提交包含摘要评论的审查来批准拉取请求或请求额外更改。

{% data reusables.search.requested_reviews_search_tip %}

## 开始审查

{% webui %}

{% data reusables.repositories.sidebar-pr %}
{% data reusables.repositories.choose-pr-review %}
{% data reusables.repositories.changed-files %}
{% ifversion fpt or ghec or ghes > 3.3 or ghae %}

   You can change the format of the diff view in this tab by clicking {% octicon "gear" aria-label="The Settings gear" %} and choosing the unified or split view. The choice you make will apply when you view the diff for other pull requests.

   ![Diff view settings](/assets/images/help/pull_requests/diff-view-settings.png)

   You can also choose to hide whitespace differences. The choice you make only applies to this pull request and will be remembered the next time you visit this page.
{% endif %}
1. Optionally, filter the files to show only the files you want to review{% if pr-tree-view %} or use the file tree to navigate to a specific file{% endif %}. For more information, see "[Filtering files in a pull request](/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/filtering-files-in-a-pull-request)."
{% data reusables.repositories.start-line-comment %}
{% data reusables.repositories.type-line-comment %}
{% data reusables.repositories.suggest-changes %}
1. 完成后，单击 **Start a review（开始审查）**。 如果已开始审查，您可以单击 **Add review comment（添加审查注释）**。

   ![开始审查按钮](/assets/images/help/pull_requests/start-a-review-button.png)

提交审查之前，您的行注释为_待处理_状态并且仅对您可见。 您可以在提交审查之前随时编辑待处理的注释。 要取消待处理的审查（包括所有其待处理的注释），请在 Conversation（对话）选项卡中向下滚动到时间表的末尾，然后单击 **Cancel review（取消审查）**。

![取消审查按钮](/assets/images/help/pull_requests/cancel-review-button.png)
{% endwebui %}

{% ifversion fpt or ghec %}

{% codespaces %}

You can use [{% data variables.product.prodname_codespaces %}](/codespaces/overview) to test, run, and review pull requests.

{% data reusables.codespaces.review-pr %}

有关在 {% data variables.product.prodname_codespaces %} 中审查拉取请求的更多信息，请参阅“[对拉取请求使用代码空间](/codespaces/developing-in-codespaces/using-codespaces-for-pull-requests)”。

{% endcodespaces %}
{% endif %}

{% ifversion fpt or ghes > 3.1 or ghec %}
## 查看依赖项更改

{% data reusables.dependency-review.beta %}

如果拉取请求包含对依赖项的更改，您可以使用清单或锁定文件的依赖项审阅来查看更改的内容，并检查更改是否引入安全漏洞。 更多信息请参阅“[审查拉取请求中的依赖项更改](/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/incorporating-feedback-in-your-pull-request)”。

{% data reusables.repositories.changed-files %}

1. 在清单或锁定文件标头的右侧，单击 **{% octicon "file" aria-label="The rich diff icon" %}** 多差异按钮以显示依赖项审查。

   ![多差异按钮](/assets/images/help/pull_requests/dependency-review-rich-diff.png)

{% data reusables.repositories.return-to-source-diff %}
{% endif %}

## 将文件标记为已查看

在完成审查文件后，您可以将文件标记为已查看，该文件将会收起。 如果查看过的文件有更改，将会取消已查看的标记。

{% data reusables.repositories.changed-files %}
2. 在完成审查的文件的标头右侧，选择**已查看**。

   ![已查看复选框](/assets/images/help/pull_requests/viewed-checkbox.png)

## 提交审查

完成审查拉取请求中需要查看的所有文件后，提交您的审查。

{% data reusables.repositories.changed-files %}
{% data reusables.repositories.review-changes %}
{% data reusables.repositories.review-summary-comment %}
4. 选择您想要留下的审查类型：

   ![具有审查选项的单选按钮](/assets/images/help/pull_requests/pull-request-review-statuses.png)

    - 选择 **Comment（注释）**留下一般反馈而不明确批准更改或请求其他更改。
    - 选择 **Approve（批准）**提交反馈并批准合并拉取请求中提议的更改。
    - 选择 **Request changes（请求更改）**提交在拉取请求合并之前必须解决的反馈。
{% data reusables.repositories.submit-review %}

{% data reusables.repositories.request-changes-tips %}

## 延伸阅读

- "[关于受保护分支](/github/administering-a-repository/about-protected-branches#require-pull-request-reviews-before-merging)"
- "[按审查状态过滤拉取请求](/github/managing-your-work-on-github/filtering-pull-requests-by-review-status)"
