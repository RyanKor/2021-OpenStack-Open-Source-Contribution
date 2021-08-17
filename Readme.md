# 2021 Open Source Contribution : OpenStack

## My Team with Open Source Contribution


<p align=center>
<img src="https://user-images.githubusercontent.com/40455392/129478937-548a7ad8-ff80-41ed-aee7-c41cd0806dce.png" width="600" />
<p/>

## 1. Work Flow

- Install OpenStack with devStack

- We are treating two version of Openstack; Wallaby (LTS) & devStack Master branch (Latest)

- Find bugs, make documentations, and if possible, commit your codes into OpenStack repo.


## 2. Work History

- [2021.08.07 Team Meeting on Google Meet](https://equus3144.medium.com/%EC%98%A4%ED%94%88%EC%86%8C%EC%8A%A4-%EC%BB%A8%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-1%EC%A3%BC%EC%B0%A8-%EB%A7%88%EC%8A%A4%ED%84%B0-%EC%B1%8C%EB%A6%B0%EC%A7%80-%EA%B8%B0%EA%B0%84-%EC%A7%84%ED%96%89-631c88d7dd58)

  - Mentors will explain the structure of OpenStack and let us know how to install OpenStack with devStak for two hours.

- [2021.08.14 Sprint Day in Open Up](https://equus3144.medium.com/%EC%98%A4%ED%94%88%EC%86%8C%EC%8A%A4-%EC%BB%A8%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-1%EC%A3%BC%EC%B0%A8-%EC%8A%A4%ED%94%84%EB%A6%B0%ED%8A%B8-%EC%98%A4%ED%94%88%EC%8A%A4%ED%83%9D-%EC%84%A4%EC%B9%98-%EB%94%94%EB%B2%84%EA%B9%85%ED%95%98%EA%B8%B0-be44aed886)

  - Install LTS & Latest version of OpenStack.
  
  - Do trouble shooting and connect network in the deployed environment; Cafe 24 VM
  
- [2021.08.17 Team Meeting on Google Meet]()

  - [Second Week Team Assignment](https://play.openstack-kr.org/pages/viewpage.action?pageId=12943414)

- [2021.08.21 Sprint Day in Open Up]()
  
## 3. Error Logs (Setup : Cafe 24 Cloud)

#### 1. Ubuntu 20.04 Python3 `simplejson` Package Error
> Error Explanation : “Error: Cannot uninstall ‘simplejson’. 
> It is a distutils installed project and thus we cannot accurately determine which files belong to it which would lead to only a partial uninstall.

**Solution**
  - If you are trying to install the latest version of devStack in Ubuntu 20.04(the latest version of ubuntu), you will see a confilct of python package.
  - **you will not see this bug if you are using the stable version of devStack (Wallaby) in Ubuntu 18.04**
  > \> sudo dpkg -l | grep simplejson # find the package which has a string 'simplejson'
  
  > \> sudo apt remove python3-simplejson # remove this in the python packages.
  
---
#### 2. Ubuntu 20.04 Python3 `pyasn1-modules` Package Error
> Error Explanation : “Error: Cannot uninstall ‘pyasn1-modules’. 
> It is a distutils installed project and thus we cannot accurately determine which files belong to it which would lead to only a partial uninstall.

**Solution**
  - If you are trying to install the latest version of devStack in Ubuntu 20.04(the latest version of ubuntu), you will see a confilct of python package.
  - **you will not see this bug if you are using the stable version of devStack (Wallaby) in Ubuntu 18.04**
  > \> sudo dpkg -l | grep pyasn1-modules # find the package which has a string 'simplejson'
  
  > \> sudo apt remove python3-pyasn1-modules # remove this in the python packages.

---
#### 3. Ubuntu 20.04 & devStack Master Branch, Internet Disconnection Error

> Error Explanation : There is the internet disconnection error after OpenStack installed in Ubuntu20.04.

- My team has set up OpenStack with the whole same process of Wallaby, but we cannot use the network after we create a new instance in it.

**Solution**
  - We are still searching the solution why it occurs (we assume we can search iptables with trouble shooting)


