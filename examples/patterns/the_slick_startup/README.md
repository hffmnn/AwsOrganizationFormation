# The Slick Startup

## Tagline

`The Slick Startup` is a startup, that's new to AWS but knows about the problems that come up when using a new tool without having at least some idea what is going on.

One of the first things they found out is, that the AWS console is nice for testing out things quickly, but that this is not a solution that scales very well. As an aspiring unicorn, they also know that the team might grow from currently 2 software engineers to the size of Facebook end of next quarter.
Because of that, they want to use multiple AWS Accounts via AWS Organizations from the beginning and they came up with this requirements.

They:

- want to setup different AWS Accounts for different environments (called `Production` and `Development`)
- want to setup one AWS Account for the (user)-account management (called `SharedUsers`)
- want to use the organization root account for billling only
- allow developers to deploy to `Development`, even through a local CLI for quick feedback cycles
- give developers readonly access to the `Production` console
- allow CI to trigger CloudFormation deployments (setup with best practices, e.g. don't give CI admin access, assume roles...)
- show a dashboard in the office that shows the every-day doubling number of users (access to logging/monitoring should follow best practices obviously)
- only want to deploy to one region
- want one account responsible for updating the organization (preferably via CI) // TODO: Who's allowed to push then?
- ...

TODO:

- how to have the `OC::ORG::MasterAccount` not to be the super user account?
