# .github

Default config for every repo in the BePartnerLabs organization.

- `.github/labeler.yml` and `.github/release-drafter.yml`: config for the reusable workflows in [centralized-workflows](https://github.com/BePartnerLabs/centralized-workflows).
Work is split in three levels, each a sub-issue of the one above:

- `.github/ISSUE_TEMPLATE/epic.yml`: an epic, the business domain to deliver; it can span several releases and closes when all its stories are done.
- `.github/ISSUE_TEMPLATE/story.yml`: the user story form (story, functional and non-functional requirements, technical criteria, acceptance tests, DoR, DoD, notes).
- `.github/ISSUE_TEMPLATE/task.yml`: an atomic, testable task, created as a sub-issue of a story and done in one PR or one semantic commit.
- `.github/PULL_REQUEST_TEMPLATE.md`: asks which issue the PR closes, which is how release-to-project knows what to move to Released.
- `profile/README.md`: the organization's public profile.

GitHub only falls back to these templates when a repo has none of its own: a
single file in a repo's `.github/ISSUE_TEMPLATE/` hides all of the
organization's issue templates in that repo.

The story form is not tied to a project, since it cannot know which one each
repo uses. To have stories land on a project, turn on that project's
"Auto-add to project" workflow, filtered by repo.
The `epic`, `story` and `task` labels must exist in the repo, or GitHub skips them.
