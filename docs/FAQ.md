# Kraul Engine FAQ

## Is Kraul Engine the same thing as Arakul Studio?

No. Arakul Studio is the user-facing workspace. Kraul Engine is the separate engine project associated with it.

## Is Kraul an image-processing engine already?

The project is intended for image-processing workflows, but the current repository tree contains documentation and the site workflow rather than engine source code. Actual processing functionality is therefore not verified by this repository's current contents.

## Does Kraul support background removal?

Background removal is part of the stated project scope. Do not treat it as an available API until implementation code and repeatable tests demonstrate it.

## What are the exact API methods?

The current repository does not provide engine source exports to inspect, so exact public method names and signatures cannot responsibly be stated yet. The API reference is prepared to record them once implementation exists.

## Why does Docker build the project?

Docker runs Jekyll to build the documentation site for GitHub Pages. That build is separate from the runtime engine and does not prove image-processing code works.

## Does a green Actions check mean the site is deployed?

A successful build step alone is not sufficient. The workflow must upload the Pages artifact and complete a deployment job. Check the run's build and deploy jobs, then verify the live URL.

## Is QKC Engine part of Kraul?

No. QKC Engine is a separate JavaScript quiz/test engine. It has its own API, tests and documentation site.

## How should a new feature be documented?

Document the exact API contract, input validation, output, errors, limits, a runnable example, tests and implementation status. Keep planned features visibly separate from working features.

## Where is the live documentation?

- [Kraul Engine documentation](https://spaj7468-cell.github.io/Kraul/)
- [Kraul GitHub repository](https://github.com/spaj7468-cell/Kraul)
- [Arakul Studio](https://spaj7468-cell.github.io/Arakul/)
- [QKC Engine](https://spaj7468-cell.github.io/qkc-engine/)
