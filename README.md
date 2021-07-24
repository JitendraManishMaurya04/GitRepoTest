# GitRepoTest

**GIT CLI Chit-Codes:**

->Git clone Git_url                           => Used to clone/copy the Repo to local directory
->Git status                                  => Used to check the status of any changes
->Git add <file_name>                          => Used to add the file changes in local Repo
->Git Commit -m "Message"         => USed to commit chnges with message in Local Repo before Push
->Git push origin master          => Push to central repo
->Git Diff <file_name>              => Used to find the difference between previous and latest file
->Git Log                         => Used to check the logs
->git log --topo-order --all --graph --date=local --pretty=format:'%C(green)%h%C(reset) %><(55,trunc)%s%C(red)%d%C(reset) %C(blue)[%an]%C(reset) %C(yellow)%ad%C(reset)%n'
->Git Checkout <file_Chksm_id>    => Used to move to different file_id
->Git Branch <Branch_Name>          => Used to create a new Branch
->Git Checkout <Branch_Name>        => Used to move to particular branch
->Git Merge <Branch_Name>           => Used to merge Branch to Master. For this we need to be in Master branch.

=>Deleting Branches:
	->Git Branch -d "Branch_Name"     => Deleting the Branch from local
	->Git Push Origin --Delete "Branch_Name"  => Deleting the Branch from Remote Repo
	
=>Creating Tag's in Git:
	Can be used to create a reference/historic point for your code taht you can refer in future.
	When we want to create a release point for a stable version of code.
	
	->Git Tag <Tag_Name >                 => Used to create a normal tag
	->Git Tag -a <Tag_Name> -m "Message"  => Used to create a annotated tag with some message
	->Git Tag                           => Used to display the list of tag in that branch
	->Git Show <Tag_name>                 => Used to show the details of a particualr Tag
	->Git Push Origin <Tag_Name>          => Used to push tag to Remote Repo
	->Git Push Origin --Tags / Git Push --Tags   => Used to push all the tags
	->Git Tag -d <Tag_Name> / Git Tag --delete <Tag_Name>     => Used to delete a tag
	->Git Push Origin --Delete <Tag_Name>  => Deleting the Tag from Remote Repo
	->Git checkout -b <Branch_Name> <Tag_Name>  =>Creating a brnach from a tag and that will have data at that point.
	->Git Tag <Tag_Name> <Checksm_Id>    => Used to create a from past checksum ID
	
=>GIT REBASE:
	-> Git rebase master
	
	* Difference between Merge vs Rebase:
			#Merge:
				->It is a non-destructive operation
				->Exisiting branches are not changed
				->Creates a new commit in the branch
			
			#Rebase:
				->Moves the branch to begin from the tip of the master branch
				->Re-Writes the project history
				->We get much cleaner and linear project history
				
GIT ISSUES RESOLVE:

=>GIT message change after commit and should be used when working alone
	->git commit --amend -m "Message" 
	
=>GIT message change/ Created a file or code which we wanted to be part of last commit
	->git commit --amend
	
=>By mistake commited in Master but now want to commit to different branch
	->git cherry-pick <checksum_id>   =>Checkout to different branch and then use this command
	->git reset <checksum_id>  		  =>Checkout to Master and then use the reset command with Checksum_id 
								        we want to goto. This will move the changes to working directory.
	->git clear -df                   => To delete and untracked changes which are not added to staging
	
=> To get a list of all the activites we are doing:
	->git reflog
	
=>To create a backup of any historic log point/to get a file which may have been deleted:
	->git reflog
	->git checkout <Checksum_id>       =>Goes to the particular time in detached state
	->git brach <Branch_name>          =>Creates a backup in different branch
	->git checkout <Branch_name>       =>Moves to the branch
	
=>We want to revert the changes which we did but others have already chekout that commit:
	->git revert <checksum_id>         =>It will commit on top of last commit and UNDO all the changes 
										 without chnging the history.
