How to fix apt update EXPKEYSIG 1F3045A5DF7587C3

Problem:
While running sudo apt update:
It shows 
Err:14 https://repo.skype.com/deb stable InRelease
  The following signatures were invalid: EXPKEYSIG 1F3045A5DF7587C3 Skype Linux Client Repository <se-um@microsoft.com>

Solution
Delete and re-add the skype key using using
sudo apt-key del 1F3045A5DF7587C3
curl https://repo.skype.com/data/SKYPE-GPG-KEY | sudo apt-key add -

After that, the error should be fixed and you can run
sudo apt update
again
