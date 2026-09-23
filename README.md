# Mad Libs activity

You'll use Git and GitHub to add words or a story to a shared Mad Libs app. The
goal is to practice the full collaboration loop: fork, branch, edit, test,
commit, push, open a pull request, review, and merge.

## 1. Form a group

Work with the people near you and choose one computer. Everyone should follow
the steps and be able to explain what each Git or GitHub action does.

Your instructor will assign your group one of these contributions:

- nouns
- verbs
- adjectives
- adverbs
- a new story

## 2. Open an issue

In the original repository, [open an issue](https://github.com/yale-mgt-656-fall-2026/madlibs-starter/issues/new)
describing what your group plans to add. Give it a short title and list your
group members in the description. Note the issue number; you'll connect your
pull request to it later.

Your instructor will use the class issues to demonstrate labels, a milestone,
and a project board. These tools make the type, deadline, owner, and status of
work visible without a separate status report.

## 3. Fork the repository

Click **Fork** near the upper-right corner of this GitHub page, keep the default
settings, and click **Create fork**.

A **fork** is your group's copy of this repository on GitHub. It is connected to
the original repository so that you can propose sending your changes back.

Make sure the repository owner shown at the top of the resulting page is you,
not `yale-mgt-656-fall-2026`.

## 4. Open a Codespace

From your fork, click **Code**, select **Codespaces**, and click **Create
codespace on main**. GitHub will open a browser-based version of Visual Studio
Code. Setup may take a minute; wait for the terminal to finish running
`npm ci`.

## 5. Preview the app

In the file explorer, right-click `index.html` and select **Show Preview**. You
can open the preview in the editor or in a browser tab.

Click **New story** a few times to see how the existing words and story
templates are combined.

## 6. Create a branch

Open the terminal in your Codespace and create a branch for your contribution:

```sh
git switch -c bald-chicken-new-verbs
```

Use a different short, descriptive branch name with no spaces, such as
`fire-lion-new-stories` or `sleek-deer-new-adverbs`.

A branch keeps your proposed change separate from the repository's `main`
branch until it has been reviewed and merged.

## 7. Make your contribution

### Adding words

Create a new file in the directory for your assigned kind of word. For example,
a group adding verbs might create `js/verbs/bald-chicken.js` with this content:

```js
verbs = verbs.concat([
    'dance',
    'juggle',
    'sprint'
]);
```

Use a unique filename and your own words. Then add a matching `<script>` tag in
the `<head>` of `index.html`, next to the existing file for that category:

```html
<script src="js/verbs/bald-chicken.js"></script>
```

### Adding a story

Add another story block near the existing stories in `index.html`:

```html
<div class="story">
    The ADJECTIVE NOUN decided to VERB ADVERB.
</div>
```

Use the placeholders `NOUN`, `VERB`, `ADJECTIVE`, and `ADVERB` exactly as
written so the app can replace them.

## 8. Preview and test

Refresh the preview and confirm that your contribution appears. Then run the
automated tests:

```sh
npm test
```

Fix any reported errors before continuing. The same tests will run on GitHub
when you open your pull request.

## 9. Commit and push

First inspect your work:

```sh
git status
git diff
```

Stage the files you changed, replacing the example paths with yours:

```sh
git add index.html js/verbs/bald-chicken.js
```

Commit the staged change:

```sh
git commit -m "Add verbs for class"
```

Push your branch to your fork:

```sh
git push -u origin bald-chicken-new-verbs
```

Use your actual branch name in the final command.

## 10. Open a pull request

Return to your fork on GitHub. GitHub should display a **Compare & pull
request** button for the branch you just pushed; click it.

On the pull-request page, verify these settings:

- **base repository:** `yale-mgt-656-fall-2026/madlibs-starter`
- **base:** `main`
- **head repository:** your fork
- **compare:** your new branch

Give the pull request a clear title and briefly describe what your group added.
Add `Closes #NN` to the description, replacing `NN` with the issue number you
noted earlier. GitHub will link the issue and pull request, then close the issue
automatically when the pull request is merged. Click **Create pull request**.

If GitHub does not show the button, follow GitHub's
[instructions for creating a pull request from a fork](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork).

## 11. Review and merge

Watch the automated test shown on the pull request. A green check means the
configured test completed successfully; a red X means the test failed and the
pull request needs another change.

Review another group's pull request and leave a useful comment or approval.
Your instructor will merge the finished pull requests into the original
repository.
