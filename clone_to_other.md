
# FOR CLONNING FROM ONE GIT TO ANOTHER REMOTE REPOSITORY

git clone --mirror <source-repo-url>

# or
git clone <source-repo-url>
cd <repo-name>

# then 
git fetch --all --prune
git branch -a

# create local branches
for branch in $(git branch -r | grep -v '\->' | grep 'origin/'); do
    git checkout --track $branch;
done

# check branch
git branch

# Add the new remote repository
git remote add new-origin <new-repo-url>

# Push all branches and tags to the new remote
git push new-origin --all
git push new-origin --tags

# Verify
git fetch new-origin
git branch -r

git branch

------------------------------

