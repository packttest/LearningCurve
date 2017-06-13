# DevOps on AWS

In general, Dev means developers and Ops means Operations (infrastructure Operations). Common myth, DevOps is Dev + Ops only. But actually it is a lot more than that.

**"DevOps is the Combination of cultural philophies, practices, and tools that increases an organization's ability to deliver applications and services at higher velocity."**
<br>Ref. [https://aws.amazon.com/devops/](https://aws.amazon.com/devops/ "https://aws.amazon.com/devops/")

In other words, DevOps is all about how fast you can deliver software to the market. Continuesly new features are introduced to the production and parallely experiments are carried out to find what works and what doesn't work.
**DevOps helps to achieve:**
* Faster time to market.
* Higher quality.
* Lower cost to deliver.

**Earlier to the DevOps:**
* Devlopment was siloed.
* Expensive and slow.
* Trust issues.

**Exactly, what is DevOps?**
It is a combination of "Dev" - devlopment, "Ops" - operation and "Process" - Such as Agile. Agile can be applied to devlopment using Scrum, sprint and other agile concepts. Agile can also be applied on operations by applying infrastructure as a code and other practices. Agile methodolgies can include Scrum, Kanban, Scaled Agile Framework® (SAFe®), Lean Development and Extreme Programming (XP).

DevOps includes three main phases:
1. Automated testing and Agile. Deliver sprints in two to three weeks.
2. Continues Integration (CI). There are several tools such as Jenkins, Bamboo, etc. Once code is tested in previous phase it can be integrated. 
3. Continues Delivery (CD). It involves several steps:
* Plan, starts with a sprint planning.
* Code, write a code and store it into the repository such as Git. Developers also write 90% of automated test cases (Unit and integration), may be QA does the remaining 10% of above-UI automation and exploratory manual testing.
* Build, tools such as Ant, Maven, Gradel, etc. can be used.
* Test, tools such as Selenium, TET, Jmeter, etc. Build and test can be done automated way with the help of tools such as Jenkins.
* Release, tools such as ElectricFlow, Continnum, Automic, etc. helps to process of managing, planning, scheduling and controlling a software build through different stages and environments; including testing and deploying software releases.
* Deploy, with the help of tools such as Puppet, Chef, etc. helps to deploy code to the cloud.
* Operate, cloud vendor such as AWS, Azure or GCP. Provides on demand highly secured environent to host IT environment. 
* Monitor, tools such as New Relic, Nagio, etc. helps to monitor infrastructure.

### What is exact difference among Continues Delivery, Continues Deployment and Continues Delivery?

### Reference URLs:
* https://www.youtube.com/watch?v=I7vHqXY22gg (What is DevOps) by Brandon Kolybaba.
* https://www.youtube.com/watch?v=071rB05Oj9g (Join Us to Explore DevOps on AWS) by AWS.
* https://www.quora.com/What-is-the-difference-between-Build-and-release-engineer-DevOps-engineer (What is the difference between Build and release engineer & DevOps engineer?)
* https://en.wikipedia.org/wiki/Release_management

