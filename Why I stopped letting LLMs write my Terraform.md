# Why I stopped letting LLMs write my Terraform

I am an IT architect. Been doing system automation for years. As a cloud architect lately, I see that landing zone setup really needs some automation. Hundreds (not millions) of parameters come from business and technical requirements and actually predefine how the LZ should look.

The problem is that most of these parameters you can't get from the customer. They are distributed over tens of standards, guides, manuals, etc.

Great, LLM is a perfect tool for it. It can gather information from different non-structured sources and build a set of parametrised templates (let's say JSON). Parameters come from the user and I get an unambiguous spec of what we have to build.

Next step — create from the spec a Terraform script, execute it, and the LZ is ready. Give it to LLM too.

But no... every change in parameters and conditions gives me another LZ. Now I have to go to my big boss and explain to him why, when he asked for one small change, I bring him something cardinally different from the first version.

Not on my shift.

So I asked the LLM to build Jinja2 templates and some code (generators) that create Terraform from the spec and the templates.

Turns out there's a name for what I ended up with — Compiled AI. LLMs build the templates, deterministic code runs them.

Technical details of how I did it: [Compile-time AI for GCP Landing Zones](https://medium.com/google-cloud/compile-time-ai-for-gcp-landing-zones-2555560fbd2f)
