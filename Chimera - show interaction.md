#### ere is one example command using some standard settings for finding contacts, assuming that “protein” and “ligand” specify the desired parts of your structure:

- [ ] findclash protein test ligand overlap -0.4 hbond 0.0 reveal true

#### or if your protein was model #0 and your ligand was model #1:17 and you also want to select the contacting atoms:

- [ ] findclash #0 test #1:17 overlap -0.4 hbond 0.0 reveal true select true

Reference: 

<http://www.rbvi.ucsf.edu/chimera/docs/UsersGuide/midas/findclash.html> 
<http://www.rbvi.ucsf.edu/chimera/docs/ContributedSoftware/findclash/findclash.html>
