ReleaseTfvcTemplate Delete Token 12.1
===================

The original ReleaseTfvcTemplate.12.xaml does not remove the .token file from the packages. This version process the tokens and then remove them from the package, if set to.

1. The new workflow sequence for the token processing is as follows:
2. Assign: gets the original file name based on the .token file;
3. Remove read-only flag from x.y: removes the ReadOnly attribute from the original file for future replacement;
4. Copy x.y.token to x.y: copies the .token file over the original file;
	1. [NEW] If DeleteProcessedTokens is set
	2. [NEW] Remove read-only flag from x.y.token: removes the ReadOnly attribute from the token file for future deletion;
5) [NEW] Remove x.y.token: removes the .token file from the package.

Also, the argument **Configurations To Release** is now **Required**.