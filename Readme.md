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


  - [First Week Team Assignment](https://play.openstack-kr.org/pages/viewpage.action?pageId=12943370)

  - Mentors will explain the structure of OpenStack and let us know how to install OpenStack with devStak for two hours.

- [2021.08.14 Sprint Day in Open Up](https://equus3144.medium.com/%EC%98%A4%ED%94%88%EC%86%8C%EC%8A%A4-%EC%BB%A8%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-1%EC%A3%BC%EC%B0%A8-%EC%8A%A4%ED%94%84%EB%A6%B0%ED%8A%B8-%EC%98%A4%ED%94%88%EC%8A%A4%ED%83%9D-%EC%84%A4%EC%B9%98-%EB%94%94%EB%B2%84%EA%B9%85%ED%95%98%EA%B8%B0-be44aed886)

  - Install LTS & Latest version of OpenStack.
  
  - Do trouble shooting and connect network in the deployed environment; Cafe 24 VM
  
- [2021.08.17 Team Meeting on Google Meet](https://equus3144.medium.com/%EC%98%A4%ED%94%88%EC%86%8C%EC%8A%A4-%EC%BB%A8%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-2%EC%A3%BC%EC%B0%A8-openstack-cli-%EC%99%80-%EC%B9%9C%ED%95%B4%EC%A7%80%EA%B8%B0-133974cd1da9)

  - [Second Week Team Assignment](https://play.openstack-kr.org/pages/viewpage.action?pageId=12943414)

- 2021.08.21 Sprint Day in Open Up : No Schedule

- 2021.08.24 2nd Team Meeting

  - We have deployed our team website.
  - [Team Blog Site](https://openstack-kr-contribution-academy-2021.readthedocs.io/ko/latest/index.html)

- 2021.08.28 [2nd Sprint Day in Open Up](https://equus3144.medium.com/%EC%98%A4%ED%94%88%EC%86%8C%EC%8A%A4-%EC%BB%A8%ED%8A%B8%EB%A6%AC%EB%B7%B0%ED%86%A4-3%EC%A3%BC%EC%B0%A8-%EC%8A%A4%ED%94%84%EB%A6%B0%ED%8A%B8-%EB%8D%B0%EC%9D%B4-master-challenge-%EB%A7%88%EC%A7%80%EB%A7%89-%EC%A3%BC%EA%B0%84-d71cc5430c55)

  - [3rd Week Team Assignment](https://play.openstack-kr.org/pages/viewpage.action?pageId=15269945)

  - This is the last week of Master Challenge period.

  - The main stage will begin at September.
  
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
#### 3. Ubuntu 20.04 & devStack Master Branch, `Internet Disconnection Error`

> Error Explanation : There is the internet disconnection error after OpenStack installed in Ubuntu20.04.

<p align=center>
<img src="https://user-images.githubusercontent.com/40455392/129654755-ae727beb-133e-4ea9-a579-72f8a3b3770c.png" width="600" />
<p/>

- My team has set up OpenStack with the whole same process of Wallaby, but we cannot use the network after we create a new instance in it.

**Solution**
  - We are still searching the solution why it occurs (we assume we can search iptables with trouble shooting)

---
#### 4. Exhausted all hosts available for retrying build failures for instance `OpenStack Resource Error`

> Error Explanation : Exceed the maximum resource of openstack when you make an instance.

**Solution**

- See the image below.

<p align=center>
<img src="https://user-images.githubusercontent.com/40455392/130330257-5d39fb80-4cf7-4055-bcd8-98c7bce04b2f.png" width="600" />
<p/>

- when you see this error even though all the resources of openstack has enough space, the main reason of this error will be VCPU capacity in hypervisor menu.
- you should delete all volume & instances you don't use and re-create instance.


---
#### 5. Tox(OpenStack Documentation Tool, Sphinx Test Software) Error

> Error Explanation : `document isn't included in any toctree`
> There were several conflicts when I executed tox to commit the whole sphinx docs.

**Solution**

- See the image below.

<p align=center>
<img src="https://user-images.githubusercontent.com/40455392/131870925-a6593d8b-0ecb-4015-886e-4a0a5bcc6e09.png" width="1000" />
<p/>

- I have setup `:orphan:` the child node before commit.
- It enables the index.rst file to include the file with `:orphan:` code and recognize the whole documentation when CI works.
