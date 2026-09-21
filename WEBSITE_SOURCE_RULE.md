# Website Source Rule

## Canonical source

The `website/` directory in `amzy/PoultryInventory-App` is the single source of truth for the OvalOasis marketing website.

## Required rules

1. Never replace, regenerate, or reconstruct `website/` from an older project ZIP, build artifact, or the public website repository.
2. Existing website files and design changes must be preserved exactly unless the private source repository contains an intentional website update.
3. App-only changes must not modify or reset any file under `website/`.
4. `amzy/PoultryInventory-Website` is a deployment mirror only. Do not use it as the source for future website changes.
5. When creating project ZIPs, always copy the current `website/` directory from the private source project.
6. If there is no website change, a project update must leave the website directory unchanged.
7. Website deployment happens only after the Web App deployment succeeds, and APK deployment happens after the website stage.
