In the context of testing chips, test coverage refers to the proportion of the design which is tested. The requirements differ at different stages of the design and production.

Additional info: 
- When a chip comes off the production line it may or may not work. The choice of what/when/how much to test is an economic question. 
- Most equipment used in chip manufacture is very expensive to buy and run (**think ‘five figures’ _per hour_**) and **time on the tester is no exception**.
- Test patterns should cover **as much as possible as quickly as possible**
- A test should get the **right answer** as often as possible! 
- This means maximising **test coverage**.

## Make the chip easy to test
**Controllability and Observability!**
### Controllability
- If a circuit is deeply ‘buried’ it can be difficult to get its inputs into the required states.
- Making it controllable means that it is easy to inject test patterns to the locality. 
- This may be as simple as embedding a multiplexer in front of the block with a switch to take patterns from an easily programmed source.

### Observability
- The outputs of the Device Under Test also need to be visible. It is sometimes easier to bring them to a test port than to try and deduce their states by looking at subsequent circuits.