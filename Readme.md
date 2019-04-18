# Binary BUILDERS to R-Hub

A solution for institutions wishing to utilise and deploy R Binaries

## Background

As your aware Microsoft (as a board member of the R Consortium) 
The project is located at : https://github.com/r-hub/rhub-linux-builders

The goal is to bring binary BUILDERS to R-Hub. This project has been submitted and funded, and much progress was made, unfortunately Dirk Eddelbeuttel and Gabor Csardi are now busy with other things but having RSEs Collaborate on this could be interesting.. 

Having quickly spoken with the R team they think the following idea below of finding a source of Linux binary packages is still a good idea on its own so there some interest in exploring this further.

## Current Problems encountered

Here the problem a number of institutions and RSEs are facing when trying to utilise R and a potential solution.

Microsoft maintains a mirror of CRAN, the R software archive, called MRAN. They also snapshot it daily as  https://mran.microsoft.com/timemachine. The snapshotting is great for reproducibility because people can reference the snapshot date when creating their user environments. For example Binder lets people specify the snapshot date within the runtime.txt file so that when people install R packages, they will be fetched from the snapshot. Most R packages are delivered as source code however. This means that the packages must be compiled during installation and this can take a long time on Binder and in CI/CD.

One way of addressing this is to get binary packages from the OS vendor. For example Ubuntu offers many binary packages of the form r-cran-{packagename}. Unfortunately they only have a small subset of CRAN libraries. CRAN itself only has just enough binary packages to basically run R. As a result people use the c2d4u3.5 PPA (catchy abbreviation for "CRAN to Debian for Ubuntu R 3.5") which is referenced on the official R project's Ubuntu docs. This repository provides a large number of binary packages and enables users to bypass long compile times. However, there are no snapshots available for it.

So I think the R community would greatly benefit if MRAN could also mirror the Linux/Ubuntu c2d4u3.5 binary archive. R-based binders would deploy much faster, as would CI integrations like ours which build/deploy docker containers with Jupyter and R. I suppose a couple of advantages for Microsoft in doing this are increased engagement with the R community and the analytics that would show what packages users typically need.

### Sprint objectives

- Create any necessary documentation https://github.com/r-hub/rhub-linux-builders
- Analysis of current rhub-linux-builders based on RSEs requirements

