# Atomic Model Building using Coot

# Step01 -  Load coordinates and map

File -> Open coordinates

File -> Open Map

# Step02 - Edit one protomer

- [ ] Calculate -> Model/Fit/Refine

- [ ] Real Space Refine Zone

- [ ] Regularize Zone

# Step03 - Make Trimer from the edited protomer

- [ ] Open Map, edited Protomer coordinate file (.pdb), and the old Trimer coordinate file (.pdb)

- [ ] Calculate -> SSM Superpose -> Superpose Protein Molecules using Secondary Structure Matching -> Choose Reference Structure (old Trimer coordinate file) & Use Specific Chain -> Choose Moving Structure (edited Protomer coordinate file) & Use Specific Chain -> Apply 

- [ ] Uncheck the edited Protomer coordinate in the Display Manager 

- [ ] Delete Item -> Delete Chain 

- [ ] Edit -> Merge Molecules -> Check Moving Structure & Merge it into trimer 

- [ ] Repeat SSM Superpose & Merge, until we get the trimer

- [ ] File -> Save Coordinates -> XXX.pdb

