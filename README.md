# volodymyr-borodin/setup-ssh-key

Requires: `bash`

```yaml
on:
  pull_request:

jobs:
  example:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: volodymyr-borodin/setup-ssh-key@v2
        with:
          private-key: ${{ secrets.MY_SSH_KEY }} # echo $(cat ~/.ssh/id_rsa)
          private-key-name: id_rsa
          known-hosts: ''
      - run: HOME=/root ssh server 'echo $PATH`
```
