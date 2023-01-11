# tenant-t1-dev-repo

Here we are following environment per repository.

### Rules behind environment promotion
1. Small pull requests
2. For a environment promotion from DEV to QA,
    a. base/ folder can be directly copied to QA repo
    b. deploy/ folder can also be directly copied to QA repo
    c. co

'''code
├── base  <<-------------------------------- can be directly copied to QA repo
│   ├── kustomization.yaml
│   └── release.yaml
├── configs
│   ├── commons <<-------------------------- can be directly copied to QA repo
│   │   ├── envs
│   │   ├── files
│   │   ├── kustomization.yaml
│   │   └── values
│   ├── kustomization.yaml
│   ├── promotables <<---------------------- can be directly copied to QA repo
│   │   ├── envs
│   │   ├── files
│   │   ├── kustomization.yaml
│   │   └── values
│   └── specifics <<------------------------ can NOT be directly copied to QA repo
│       ├── envs
│       ├── files
│       ├── kustomization.yaml
│       └── values
├── deploy <<------------------------------- can be directly copied to QA repo
│   ├── kustomization.yaml
│   ├── values-patch.yaml
│   └── version-patch.yaml
└── kustomization.yaml <<------------- (kustomize build .) => renders full deployment
'''