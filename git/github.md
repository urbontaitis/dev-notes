# Working with Github organizations

``` bash
# set full read permissions if you want to clone as well private repositories
export GITHUB_ACCESS_TOKEN=
export GITHUB_ORGANIZATION=
curl -s https://$GITHUB_ACCESS_TOKEN:@api.github.com/orgs/$GITHUB_ORGANIZATION/repos?per_page=200 | jq '.[].ssh_url' | xargs -n 1 git clone
```


## Change the ssh key for a single repository

```bash
git config --add --local core.sshCommand 'ssh -i ~/.ssh/another_id_rsa`
```
