To test the file, do it the normal way. Run ganache at the default port, that should be 8545. Then, run truffle compile, migrate, and test. Make sure to delete the build folder before compiling, since compile won't run if there's already a build folder. 

Please read the README file first. Anyways, since none of the CS objects would be in the final build, I didn't use them in any tests. However, I did use the Assert.sol and DeployedAddresses.sol libraries for the tests. 

The 5 tests I wrote are as follows: 

testSetUp: This tests the setup function used in the new2playergame and newsologame functions. I only checked that the guesses and number of ships were initialized correctly. Since those two are the first and last things that the function initializes, I assume that the middle parts would only fail if one of those did. 

testNewSoloGame: This tests the newsologame function. It checks that the function works, that it is the
player's turn, and that the game number goes up.

testStartGame: Since I wrote this in Solidity, I had to do some odd things with this test. It's rather hard to look up different deployed addresses in Solidity, however, the function normally requires a second deployed address to be set as the opponent before the game play can start. To get around this, I rewrote the function so that the tester could play themselves in the test. The next two tests also have the same design features. The test shows that the encoded board is added, that the number of ships is right, and that the game starts.

testMakeMove: This tests the make a move function. This should cover the situtation where a player sinks a ship, but the game doesn't end.

testClaimWinByGameplay: This tests the Claim win function. It shows that the game ends and the winner can claim the win.
