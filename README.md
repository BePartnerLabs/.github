# .github

Default config for every repo in the BePartnerLabs organization.

- `.github/labeler.yml` and `.github/release-drafter.yml`: config for the reusable workflows in [centralized-workflows](https://github.com/BePartnerLabs/centralized-workflows).
- `.github/ISSUE_TEMPLATE/`: the issue forms (see below).
- `.github/PULL_REQUEST_TEMPLATE.md`: asks which issue the PR closes, which is how release-to-project knows what to move to Released.
- `profile/README.md`: the organization's public profile.

## Epics, stories and tasks

Work is split in three levels, each created as a sub-issue of the one above:

- **Epic** (`epic.yml`): the business domain to deliver. It can span several releases and closes when all its stories are done.
- **Story** (`story.yml`): one concrete feature of an epic: story, functional and non-functional requirements, technical criteria, acceptance tests, DoR, DoD and notes. The PR that closes its last task closes it too.
- **Task** (`task.yml`): an atomic piece of a story, proven by an automated test and done in one PR or one semantic commit.

GitHub only falls back to these templates when a repo has none of its own: a
single file in a repo's `.github/ISSUE_TEMPLATE/` hides all of the
organization's issue templates in that repo.

The forms are not tied to a project, since they cannot know which one each
repo uses. To have issues land on a project, turn on that project's
"Auto-add to project" workflow, filtered by repo.
The `epic`, `story` and `task` labels must exist in the repo, or GitHub skips them.
