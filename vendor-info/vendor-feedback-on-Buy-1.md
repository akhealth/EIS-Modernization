# Lessons Learned From "Search" Procurement
One of the goals of an agile organization is to continuously improve, by reflecting on what's happened at the end of an iteration. In government this is normally called a "lessons learned" session. The Alaska and 18F Medicaid EIS Modernization product team has been doing this at the end of every two-week sprint by holding a "retrospective" on what's worked and what needs to be improved. The Alaska team has been open by default on this project, so that stakeholders and vendors can see what progress has been made, and submit feedback.

With transparency in mind, please see our [Lessons Learned](https://github.com/AlaskaDHSS/EIS-Modernization/blob/master/vendor-info/Post-Mortem_on_the_first_Alaska_buy.v2.pdf) document that summarizes our internal reflections on [the first procurement](https://github.com/AlaskaDHSS/RFP-Search-Unification). 

In addition, we asked vendors for their feedback on the following questions:  

>### Planning process

>The planning process that led up to the RFP took some time. We prepared for the procurement through an entirely open process that included technical prototyping, defining a product roadmap, issuing an RFI, then a draft RFP, and then the final RFP. This preparation was all done on GitHub. What parts of this planning process were helpful? What parts were a burden? What would you change about this process?

>### RFP
>What are your thoughts on the final RFP? What parts of the RFP were overly burdensome?

>### Future acquisitions
>What should we change for your company to consider bidding on the next RFP? 

>Do you have any other feedback on the process?

## Summary of what we heard from the vendor community
We got helpful feedback from 12 companies that were tracking our work. Some of them bid, many of them didn't. We've anonymized these responses and grouped them under different themes.
 
Our next step will be to ensure that we incorporate and improve upon some of the more common themes for our next procurement, if possible.

### There were some common themes:

#### The vendor community appreciated the transparency. Even those that didn't bid, or disagreed with some of the process, said they appreciated that the planning was done in the open.

  * “Watching the evolution of the RFP was helpful, although GitHub isn't something we've seen used for this type of document before. It took some adjustment for those of us not familiar, and caused a bit of anxiety around staying on top of changes, updates etc. We appreciated the advance notice of the procurement and the government's transparency."

  * “It was great to see the RFP evolve in the open. It helped set clear expectations on our side about what the government expected for success.”

  * “We are impressed with the level of information and transparency around this initiative conducted by the Department. In general, many states could benefit by adopting these processes described above.”

  * “The planning process was very helpful in that it was transparent upfront and gave plenty of time to digest what was required for the response."

  * “We did not look at the final RFP, we decided not to bid before the final RFP was released, which I think is a good thing: we had plenty of information prior to the release of the RFP that allowed us to make a decision whether or not we should pursue.”

  * “We'd like to commend your process, and applaud the transparency. To be honest it's as much of an adjustment on our end, where we are so used to more formal procurement processes.”

  * “This time we engaged heavily at the beginning - read every doc you posted on GitHub - but by the time the procurement ramped up we were too busy to consider replying.”

#### Vendors that decided not to bid commonly pointed to our decision to use the .NET and Azure technology stack.

  * “In the end, our decision not to bid was driven by your choice of tech stack, which didn't align with our own team's skills.”

  * “I did not apply because the approved technology list (Microsoft stack) is not what we use.”

  * “Your tech stack was the real stumbling block for us, and we understand that is not likely to change, given your existing skills and investments. Had the scope been constrained to UX design and development, utilizing any flavor of JavaScript framework (Angular, React, Ember etc.), our skills would've aligned, and we definitely would've bid. The inclusion of .NET and Azure excluded us, since we don't have any credible experience here (Java/AWS is our sweet spot). We thought about trying to subcontract some of this experience, but in the end weren't comfortable having the Tech Lead be someone we weren't familiar with. We'll continue to monitor future RFPs to see if we are better fit for any of those.”
 
  * “The .NET tech stack isn't our sweet spot so if future bids require this, we will likely not bid.” 

  * “...In addition, the Microsoft tech stack (Azure / .NET) created a higher barrier to entry for us because at this time, our expertise is mostly in Amazon Web Services (AWS).”

  * “Expand your list of approved technologies. Code for America uses Ruby on Rails exclusively, maybe that?”

  * “We suggest more flexibility on the tech stack. Limiting yourself to a Microsoft stack limits the number of vendors who can participate.”

  * “Different technology stack (.NET/MS is a fine stack, just not our thing).”

#### GitHub was useful for vendors to see the planning process, but they commonly cited a "signal to noise" problem with notifications.

  * “GitHub was particularly not useful as a tool for tracking changes to the RFP, I'm not sure what would be better, but we found GitHub to very difficult to follow in a meaningful way. Either you had to sign up for notifications, and get deluged with every single comment on every pull request, or you had to check back manually and sort through changes, branches, etc. It was very difficult to follow.”

  * “Watching the evolution of the RFP was helpful, although GitHub isn't something we've seen used for this type of document before. It took some adjustment for those of us not familiar, and caused a bit of anxiety around staying on top of changes, updates etc. It also wasn't entirely clear when feedback and questions were encouraged, where we're more used to a formal Q&A period.”

  * “The greatest difficulty for us in tracking Github is that the site's notification setup is not geared for this use case, and we found ourselves not able to subscribe to the right "level" of updates. (We chose to be updated more frequently and risk notification fatigue, rather than risk not receiving a critical update on timing, release, scope, etc.)”

  * “The planning process was very helpful in that it was transparent upfront and gave plenty of time to digest what was required for the response. GitHub was particularly not useful as a tool for tracking changes to the RFP, I'm not sure what would be better, but we found GitHub to very difficult to follow in a meaningful way. Either you had to sign up for notifications, and get deluged with every single comment on every pull request, or you had to check back manually and sort through changes, branches, etc. It was very difficult to follow.”

  * “Since we didn't bid on this RFP, we fell out of the communication loop, so aren't aware of who the final awardees are. Do you all maintain a blog or something similar to keep everyone updated on your progress? If there was a better way to subscribe to the right level of notifications, that would give us more comfort that we're not missing any important updates.”

### There were some areas where vendors had varying opinions:

#### Most of the vendors seemed to like the tightly-scoped work and Alaska's different approach to publicly sharing the open source code that will be produced:

  * “Often we have to compete on 5 year efforts, submit hundreds of pages and then on Day 1 after a long evaluation period, the entire focus of the effort has changed. This approach is just simply better.”

  * “The final RFP described a clear, discrete scope of work, without overly burdensome response requirements. The RFP was refreshingly clear!”

  * “The final RFP was put together very well and was not overly burdensome.”

  * “We fully support the idea of starting small, iterating, and making adjustments as you learn. We expect to look more carefully at future RFPs whose scope is a better fit for where [our company] can bring highly differentiated value.”

  * “The content requested was minimal so if we had decided to bid, it would not have been a large effort on our part to submit a response. The orals were useful to us and we'd welcome that approach again.”

#### However, this was not a universal opinion. Two vendors had comments that disagreed with the approach:

  * “Requirements need to be better defined. Uncertainty of where open source could go.”

  * “One suggestion is around the detail concerning the specific scope surrounding proposed future modules. We were unaware as of 2 months ago, if the roadmap included module definition other than the first RFP for the search function.”

  * “A couple items were a bit unusual for what we have seen previously regarding procurements in the Integrated Eligibly area. First, the size and scope of the SOW. From a vendors perspective, there are demands on our area experts and decisions need to be made on focus and allocation of these resources. Careful evaluation is performed on the size, scope, and duration of the contract for these individuals. An additional area involves the ongoing development and uploading of code to the public. This is not an issue so much for this search function scope, however many vendors have invested significantly on development of their modules and may be challenged for some areas to comply with the custom developed code made directly available to the public.“

  * “[Same Company] fully supports modularity, agile and working in a transparent multi-vendor environment. To increase interest, we suggest larger buckets of scope and the ability to leverage pre-invested and built modules and technology that would effectively integrate within the AK project. One example is if case management was defined as a SOW area and we could leverage a significant portion of our configuration.”

#### The state-mandated Alaska-based-business preference was cited as something that might limit participation from non-Alaskan vendors.

  * “The AK residency rqmts may cause us not to bid on the next effort. We researched the business license and other rqmts, contacting a law firm in AK to assist with some registration questions. It makes little sense to spend that kind of money and time up front with the hopes of gaining points towards winning, but no idea if we'd actually win. Your AK-based incumbent automatically has a huge advantage there.”  [*Note: The incumbent from the last contract was not an Alaskan firm. But the comment is still relevant.*]

  * “The local requirements were not egregious, but there was some preference for Alaska companies that pushed us towards not responding.”

### We’d like to once again thank all of the vendors that are tracking our work and those vendors that took the time to provide this valuable feedback.  We hope you’ll see improvements in our next procurement.  

### Please keep in mind if you have questions or comments as we continue, please submit them as [GitHub Issues](https://github.com/AlaskaDHSS/EIS-Modernization/issues) on our primary project repo.
