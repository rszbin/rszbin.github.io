---
layout: post
title: 'TeamCity Kotlin DSL'
categories: tools
---

## Versioned Settings
TeamCity requires write access to persist changes made in the UI back to the project repository.

When the build starts: use latest settings from VCS which gives you the latest build settings from VCS

Settings format: use Kotlin. The Kotlin you write generates xml behind the scenes.

### a project block defines the high level TeamCity project, and includes a build configuration
project {
    buildType(Build)
}

### A buildType is what the TeamCity UI refers to as a Build Configuration
object Build : BuildType({
    name = "Build"

    vcs {
        root(DslContext.settingsRoot) // store settings.kts in .teamcity folder in repository root
    }

    steps {

    }

    triggers {
        vcs { // uses the default VCS config, polling the repo every 60 seconds
        }
    }
})