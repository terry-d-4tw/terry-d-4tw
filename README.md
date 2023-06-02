# Hackathon [hack-your-portfolio](https://hack-your-portfolio.devpost.com)

# Action Plan (WIP / Draft)

- [x] Create a `hidden` repo on GitHub that has the same name as the username/ownername with basic README
- [x] Set up some elementary testing via GitHub Actions (e.g. assert 'I love Hackathons and Test Driving' is in README)
- [x] Deploy to GitHub Pages and set up GitHub to auto-deploy on code change
- [x] Set up elementary JAMStack / Jekyll framework
- [ ] experiment with Jekyll themes
- [ ] explore some cool JavaScript to spice up JAMStack if theme does not suffice
- [ ] explore some APIs to connect to JAM Stack
- [ ] OPTIONAL - enhance CI/CD pipeline
- [ ] OPTIONAL - enhance basic testing
- [ ] OPTIONAL - explore OpenTelemetry
- [ ] OPTIONAL - explore Data / Telemetry visualisation - m.b. explore Grafana

# Logs

## Set up some elementary testing via GitHub Actions (e.g. assert 'I love Hackathons and Test Driving' is in README)

```sh
if curl -s -N 'https://github.com/terry-d-4tw/' | grep -q "I love Ruby too"; then
 echo "it worked! 🎉"; exit 0; else
 echo "it did not work 😔"; exit 1
fi
```

## Set up elementary JAMStack / Jekyll framework

just create a
```yaml
# _config.yml

theme: minima # minima is one of Jekyll's default themes
```

if you want to be able to develop locally and have nice things that come out of the box with Ruby's Jekyll installer (i.e. default 404 page and some extra configs) do:

```sh
cd ../
jekyll new terry-d-4tw --force # you need force since you are in a non-empty directory
cd terry-d-4tw
# ensure to add `webrick` gem to your gemfile, otherwise you will get an error when running `bundle exec jekyll serve`
bundle add webrick
```

now we can run it locally via

```sh
bundle exec jekyll serve -P 4001
```

## experiment with Jekyll themes

Out of the box GitHub supports [these themes](https://pages.github.com/themes/) - they are pretty basic, and in my view minima looks the best, but yet there is a lot to be desired.

Alternative is to use [Minimal Mistakes theme](https://github.com/mmistakes/minimal-mistakes), which is more involved, but hey, that's what we want, right?

Cool plugings/snippets/scripts:
{% raw %}
```sh
{% include_relative README.md %} # include a file from the same repo

# add table of conents
* toc
{:toc}
```
{% endraw %}
# Judging Criteria

## Technology
   How technically impressive was the hack? Was the technical problem the team tackled difficult? Did it use a particularly clever technique or did it use many different components? Did the technology involved make you go "Wow"?
## Design
   Did the team put thought into the user experience? How well designed is the interface?
## Learning
   Did the team stretch themselves? Did they try to learn something new? What kind of projects have they worked on before?
## Adherence to Theme
   Does the hack adhere to the event's theme? Does it implement that theme fully or just partially?
## Originality
   Has this project been done before at hackathons in the past? How creative is their project in solving the problem at hand?
## Completion
   Does the hack work? Did the team achieve everything they wanted?
