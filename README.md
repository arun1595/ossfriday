# Open Source Friday

Open source is made by people just like you. This Friday, invest a few hours contributing to the software you use and love.

## What is this?

Open Source Friday is a movement to encourage companies, people and maintainers to contribute a few hours contributing to open source every Friday.

*Alternative name: 52 pull requests*

Things that worked well for @andrew's 24 Pull Requests that we're replicating:

- **opt-in for maintainers** - only point to projects that maintainers have agreed so we don't send a swarm of extra maintainer work to someone who doesn't want it or can't handle it.
- **wisdom of crowds** - if lots of people are doing the same thing at the same time more people will make an effort to join in
- **avoid rewards** - Getting free t-shirts or other kinds of gifts tends to bring out bad behaviour like PRs that change a single line of whitespace, which waste maintainers time and energy, the rewards should be less tangible

Things we're trying:

- **not tied to pull requests** - we're also considering maintainers events on issues, pushes, pull request reviews and releases.

- **Three target audiences** - Individual contributors, maintainers and companies are the three types of audience we should be catering to, with documentation for each one on how to get involved.

## Development

Source hosted at [GitHub](https://github.com/ossfriday/ossfriday).
Report issues/feature requests on [GitHub Issues](https://github.com/ossfriday/ossfriday/issues).

### Getting Started

Register a [new GitHub OAuth application](https://github.com/settings/applications/new).

* Set the homepage to `http://localhost:3000`.
* Set the authorization callback URL to `http://localhost:3000/users/auth/github/callback`.

Create the config file for the client ID and secret generated for your GitHub OAuth application:

```
cp config/application.example.yml config/application.yml
```

Update `config/application.yml`, setting the `github_client_id` and `github_client_secret`.

The environment variables are managed using [figaro](https://github.com/laserlemon/figaro).

#### Bootstrapping the Application

If you're on macOS, have Homebrew installed, and you've set the environment variables above to get started run:
```bash
./script/bootstrap
./script/setup
./script/server
```

Otherwise, no worries! You can follow these instructions to install a local server.

First, you'll need to install Ruby. We recommend using the excellent [rbenv](https://github.com/rbenv/rbenv),
and [ruby-build](https://github.com/rbenv/ruby-build)

```bash
rbenv install
```

Next, you'll need to make sure that you have PostgreSQL installed. On Debian-based Linux distributions you can use apt-get to install Postgres:

```bash
sudo apt-get install postgresql postgresql-contrib libpq-dev
```

On Windows, you can use the [Chocolatey package manager](http://chocolatey.org/) to install Postgres:

```bash
choco install postgresql
```

Now, let's install the gems from the `Gemfile` ("Gems" are synonymous with libraries in other
languages).

```bash
gem install bundler && rbenv rehash
bundle install
```

Once all the gems are installed, we'll need to create the databases and
tables. Rails makes this easy.

```bash
./bin/setup
```

Now all we have to do is start up the Rails server and point
our browser to <http://localhost:3000>

```bash
./script/server
```

### Note on Patches/Pull Requests

 * Fork the project.
 * Make your feature addition or bug fix.
 * Add tests for it. This is important so we don't break it in a future version unintentionally.
 * Send a pull request. Bonus points for topic branches.

### Code of Conduct

Please note that this project is released with a [Contributor Code of Conduct](CODE_OF_CONDUCT.md). By participating in this project you agree to abide by its terms.

## Copyright

Copyright (c) Open Source Friday contributors. See [LICENSE](https://github.com/ossfriday/ossfriday/blob/master/LICENSE.txt) for details.
