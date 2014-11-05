ReleaseTfvcTemplate 12.1
===================

The original ReleaseTfvcTemplate.12.xaml does not remove the .token file from the packages. This version process the tokens and then remove them from the package.

The new workflow sequence for the token processing is as follows:

1) Assign: gets the original file name based on the .token file;
2) Remove read-only flag from x.y: removes the ReadOnly attribute from the original file for future replacement;
3) [NEW] Remove read-only flag from x.y.token: removes the ReadOnly attribute from the token file for future deletion;
4) Copy x.y.token to x.y: copies the .token file over the original file;
5) [NEW] Remove x.y.token: removes the .token file from the package.
