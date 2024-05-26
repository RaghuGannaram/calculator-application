## Instructions to add submodules to this repo

```sh
git submodule add git@github.com:RaghuGannaram/addition-service.git

git submodule add git@github.com:RaghuGannaram/subtraction-service.git

git submodule add git@github.com:RaghuGannaram/multiplication-service.git

git submodule add git@github.com:RaghuGannaram/division-service.git

git submodule add git@github.com:RaghuGannaram/calculation-service.git
```

## Instructions to clone this repo with submodules

```sh
git clone 'url/of/this/repo' .
git submodule --init
git submodule --update
```

or

```sh
git clone --recurse-submodules 'url/of/this/repo'
```

## Working with Submodules

#### Changes in Submodules

1. Make changes inside a submodule:

    ```sh
    cd path/to/child_repo_1
    git add .
    git commit -m "Made changes in child_repo_1"
    git push origin main
    ```

2. Update the parent repository to point to the new commit:
    ```sh
    cd ../..
    git add path/to/child_repo_1
    git commit -m "Updated child_repo_1 to latest commit"
    git push origin main
    ```

#### Removing Submodules

If you need to remove a submodule:

```sh
git submodule deinit -f path/to/child_repo_1
rm -rf .git/modules/path/to/child_repo_1
git rm -f path/to/child_repo_1
```

## Useful submodule commands

#### Check the status of submodules:

-   Check the status of submodules:

    ```sh
    git submodule status
    ```

-   Fetch updates for each submodule:

    ```sh
    git submodule foreach git fetch
    ```

-   Listing submodules and their status:

    ```sh
    git submodule foreach 'echo $name && git status'
    ```

#### Update submodules in parent repository:

-   Update single submodule:

    ```sh
    cd path/to/child_repo_1
    git pull origin main
    cd ../..

    git add path/to/child_repo_1
    git commit -m "Updated child_repo_1 to latest commit"
    git push origin main
    ```

-   Update all submodules to the latest commit:

    ```sh
    git submodule update --remote --merge

    git add .
    git commit -m "Updated all submodules to latest commit"
    git push origin main
    ```

-   Manually update all submodules:

    ```sh
    git submodule foreach git pull origin main

    git add .
    git commit -m "Manually updated all submodules"
    git push origin main
    ```

#### Other submodule commands:

-   List all submodules:

    ```sh
    git submodule
    ```

-   Add a new submodule:

    ```sh
    git submodule add <url> [path]
    ```

-   Initialize submodules:

    ```sh
    git submodule init
    ```

-   Deinitialize a submodule:

    ```sh
    git submodule deinit [--all | <path>]
    ```

-   Synchronize submodules:

    ```sh
    git submodule sync [--recursive]
    ```
