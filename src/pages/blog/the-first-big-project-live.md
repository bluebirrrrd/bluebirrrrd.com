---
templateKey: blog-post
title: The first big project live!
date: 2021-04-07T13:28:00.000Z
description: Red Hat Learning Subscription Premium is available in North America.
featuredpost: false
featuredimage: /img/blog-index.jpg
tags:
  - accomplishments
  - red hat
  - training
---
I became a manager in July of 2020, and in September we kicked off RHLS Premium. This was the first large project I didn't get to code, but got to manage the engineering side.

After 6 months of research and development, a huge cross-functional effort from the whole Red Hat Training department, and a few weeks of a closed Beta, we're finally live! See the announcement [here](https://www.redhat.com/en/about/press-releases/red-hat-launches-red-hat-learning-subscription-premium?source=pressreleaselisting).

I want to remember this moment, because just like any human, I tend to forget the good things and keep cringing on the bad ones years later. This release is a good thing, and I'm incredibly proud of the work done by the team.

## What is it?

RHLS Premium is a new subscription tier offered by Red Hat Training, which allows users to not only take the courses in a self-paced manner as a text or video (both with lab exercises), but also to get access to Red Hat certified instructors by attending live sessions on all the courses we currently offer. A student can sign up for a 3-hour-long live session and learn a part of a course through live virtual training. This gives them an opportunity to ask questions, be more engaged and practice with someone who has the expertise on a topic.

There's several other features that are offered as part of this tier, but attending live sessions is a differentiator from other subscription tiers we offer.

## What has worked well in the process?

We had several design rounds to figure out the best experience possible with input from many stakeholders. A lot of thought was given to the session sign-up process, as well as an experience of accessing live sessions by students and instructors.

We've had several integrations introduced as part of this effort, and going with an API-first approach has been of huge help. At the beginning of the integration process with the LMS, for example, the teams have defined a set of endpoints needed on each side, as well as the structure of the information that needs to be sent. As a result, when the APIs were implemented on each side, testing went almost seamlessly, and both RHLS and LMS have been sending and accepting the information seamlessly.

Having clear priorities has been especially helpful when the development began. We focused on the MVP of being able to view the sessions catalog & schedule, sign up for them and attend the training as Phase 1, and have significantly improved the instructor experience and reporting capabilities as Phase 2, together with adjusting the student experience according to the feedback we've received during Beta.

Great technical leadership from one of my associates. Prima has stepped up and made sure that everyone was on the same page about how things should work. It took a lot of communication, but as a result, there were barely any changes requested to the APIs and frontend features implemented.

I also appreciated the fact that the team has thought about the infrastructure surrounding the go-live beforehand. We've deployed the app early and often on our development OpenShift cluster, and have merged the functionality to the main branch sooner than planned. That came especially handy when we realized that we have to deploy to production a week sooner than originally planned for a Beta, as the Beta customers had to sign up for sessions at least some time ahead of the session start.

## What did not go well?

As I mentioned in a paragraph above, we didn't realize we had to go live sooner until 1.5 weeks before the Beta date. Everyone was thinking about the first day of Live Sessions training as the start date of the Beta, but we actually had to allow the students to sign up for sessions a week earlier. I'm happy we had the app ready for deployment much earlier than originally planned. For the next projects, I'll clarify the timelines early and often (and will continue to have things ready way sooner than needed :) )

There were rare occasions of work done twice. One developer would implement a feature, and then they (and the rest of the team) would find out the other person has implemented the same thing either a few days earlier, or at around the same time. While we do have a concept of owning the work in Rally, increased transparency on the team would have helped avoid the situation altogether. This is something I'm still trying to figure out how to solve.

## Conclusions (for now)

With Premium finally available to the customers, I'm very proud of the product we got to deliver. There has been so many parts at play, from design considerations to integrations with other services, and the team has developed an amazing product. We're currently looking forward to the feedback from the larger audience, and I hope that RHLS Premium will be useful for the students as it was exciting for us to implement.
