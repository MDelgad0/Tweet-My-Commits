# Tweet My Commits
Git hook setup for Tweet my commits

## Installing Twurl

Twurl can be installed using ruby gems:

```bash
gem install twurl
```

## Getting Started

If you haven't already, the first thing to do is apply for a developer account to access Twitter APIs:

```
https://developer.twitter.com/en/apply-for-access
```

After you have that access you can create a Twitter app and generate a consumer key and secret.

Just copy the consumer key and secret in the ```.bashrc``` file.

open the .bashrc file:
```bash
vim ~/.bashrc
```
copy the consumer key and secret:
```bash
export TWITTER_CONSUMER_KEY=your_consumer_key_here
export TWITTER_CONSUMER_SECRET=your_consumer_secret_here
```

reload env variables:
```bash
source ~/.bashrc
```

execute the pre-authorize script:

```bash
sh pre-authorize.sh
```

This will return an URL that you should open up in your browser. Authenticate to Twitter, and then enter the returned PIN back into the terminal. Assuming all that works well, you will be authorized to make requests with the API. Twurl will tell you as much.

Now just copy the ```post-commit``` script and paste itinto ```.git/hook/``` of any project.

```bash
cp post-commit ~/my-awesome-git-project/.git/hooks/post-commit
```