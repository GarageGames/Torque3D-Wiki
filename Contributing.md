Thank-you for wanting to contribute to Torque 3D!  Please see the following for more information:

* [Launch Blog](http://www.garagegames.com/community/blogs/view/21886)
* [Steering Committee Charter](Steering-Committee-Charter)
* [Announcing the New Torque 3D Steering Committee!](http://www.garagegames.com/community/blogs/view/21966)
* [T3D Steering Committee Meeting Notes - 2012](http://www.garagegames.com/community/forums/viewthread/131875)
* [T3D Steering Committee Meeting Notes - 2013](http://www.garagegames.com/community/forums/viewthread/132828)

Open Source Software Agreement
------------------------------
Before contributing to the Torque 3D code base we require that you sign the *Open Source Software Agreement* on the GarageGames site.  This agreement is designed to protect the integrity of the Torque 3D project as well as GarageGames LLC.  This is a common practice with large scale open source projects such as those under the Apache Software Foundation ([individual](http://www.apache.org/licenses/icla.txt) and [corporate](http://www.apache.org/licenses/cla-corporate.txt)) and [Oracle](http://www.oracle.com/technetwork/community/oca-486395.html).

To sign the *Open Source Software Agreement* please follow these steps:  

1. Log into your account at [GarageGames.com](http://www.garagegames.com).  
2. Go to your [account settings](http://www.garagegames.com/account/settings) page.  
3. Review the Open Source Sotware Agreement on that page and fill in the required fields.  
4. While optional, it would be great if you also filled in your GitHub account name so we have a quick reference to who has already signed the agreement.  
5. Click on one of the three radio button choices at the bottom of the section.  
6. Click on the `Save` button at the bottom of the settings screen.  

It is important to note that once you have accepted the agreement it is not possible to make any changes to the information you have entered.  Unfortunately, this also means your GitHub account name at this time, although it will be moved to a separate section in the future.  For now, double check that you have entered it correctly before clicking on the `Save` button.

Branches
--------
There are two branches: *master* and *development*.  The *master* branch contains the current stable version of Torque 3D.  The *development* branch is where all work is done prior to it being moved to the *master* branch as determined by the Steering Committee.

### Using the development branch
To start using the *development* branch you will need to create your own fork of the repository:

1. Create your own fork of the Torque 3D repository by using the **Fork** button on GitHub.
2. Clone your Torque 3D fork to your computer.
3. Check out the *development* branch from the Git command line: `git checkout development`
4. Add an upstream remote: `git remote add upstream https://github.com/GarageGames/Torque3D.git`

To pull changes from the GarageGames/Torque3D *development* branch into your developer fork: `git pull upstream development`

To submit your changes back to the GarageGames/Torque3D *development* branch, use the **Pull Request** page from GitHub to make a request from your fork into the *development* branch.

## Code style guidelines
The [Code Style Guidelines](https://github.com/GarageGames/Torque3D/wiki/Code-Style-Guidelines) page is to be referred to in order to help maintain consistency throughout the Torque 3D codebase.