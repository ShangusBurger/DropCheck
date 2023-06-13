Howdy!

DropCheck is an automated file submission application that checks files for metadata before allowing submitters to move on. It makes use of AppleScript, and was made to be used on shared servers, where a system admin can selectively assign users read/write permissions.

How this script works:
1. Receive a reference to a file someone is trying to submit (either dropped on app or prompted to select)
2. Run exifTool on that file, a video metadata checker
3. Compare exifTool's measured info with the standards we set for submissions
4. If there's something that doesn't match, remind students of our submission standards, otherwise:
5. Prompt student for a screening day, and give them one final warning about aborting the upload
6. Copy the file to "Tools/Copy Buffer", rename it with a suffix like "CHECK_" or "GOOD_", tag it yellow if it was submitted with errors, then move it to the proper folder associated with the screening day
7. Give students a green checkmark



Things to do when porting this onto a new system / prepping for Bijou:

	In Finder:
-Rename and set write-only files (Monday-Friday folders)
-Rename and set read-only files (README, submit-icon, check-icon, exifTool, SubmitToBijou.scpt)
-Make sure Copy Buffer is read&write for everyone
-Although it's hidden, you may want to rename "Bijou" folder to something like "DO NOT SUBMIT DIRECTLY HERE", or other festival name. 

	In SubmitToBijou.scpt:
-If you changed folder "Bijou", you must change that text in SubmitToBijou.scpt
-Update submissionDays to the dates of the screenings (must match folder names)
-Update all prompts/dialogs to your liking
-update URLs and emails
-If any specifications have changed, change correctSpecifications (may take some trial and error, exiftool is iffy sometimes with how it writes file data)
-Re-export .scpt with updates as a run-only Application
	
	Extra Aesthetics:
-Add an icon to the application
-hide anything you don't need people seeing

Happy Submitting!
Shane