# Bitmark mining incentive mechanism improvement

---

# Reward

Miner account information is stored inside each block. However, on the Bitmark blockchain, a mining reward is not given to a miner when the block is mined; instead, the reward is given to a miner when transactions in the miner’s block are transferred. The miner is rewarded 0.001 LTC for every transfer of a digital asset, which means if a miner mines a block with popular digital assets, they get more rewards.

For example, miner A mines block number 1000, and this block contains a digital asset. After some period of time, the owner of the digital asset transfers the asset to another account. Once the transfer record has been put into the blockchain, miner A receives a mining fee of 0.001 LTC. If the new owner of that digital asset transfer again, then miner A is rewarded an additional 0.001 LTC.

```jsx
Po-Wei

Please also consider mining rewards for our v2. I’d love to hear your thoughts here too. 

Sean

---------- Forwarded message ---------
From: Sean Moss-Pultz <sean@bitmark.com>
Date: Mon, Jan 28, 2019 at 20:04
Subject: Re: Bitmark blockchain mining incentives
To: Noah S. Jessop <nsjessop@gmail.com>

Noah

I wanted to follow up on the below with some new thoughts... 

To refresh your memory, currently miners earn Bitcoin or Litecoin micro-payments per transaction, but transaction fees are very high at present and a lot of these have to be accumulated for a long time before it is practical to consolidate them.

Each Bitmark block contains a foundation record containing Miners Bitmark account, Bitcoin and Litecoin addresses.

One possible addition is to setup an internal Mining-Share that would be earned in the following way:

* one new share per transaction in the block

* a transaction can be immediately verified if the owner's share has:
  balance > (len(transaction) + 1023)>>10  [to pay more for asset records]

* the above shares would not be active on a miner's account until 100
  blocks have been generated to deal with short duration forks

The miners would need to sell their shares to users of the blockchain to make this work. Users with mining share balance would have their
transactions automatically verified and eligible for mining sooner. Normal Bitcoin or Litecoin micro-payments are unaffected.

* possibly introduce a share grant with escrow to automate transfer of a 
  number of mining shares to Bitmark user accounts in direct exchange 
  for larger than micro-payments of Bitcoin or Litecoin

I’m going to be underwater for the next two days getting ready for Chinese New Year. But maybe we can speak later in the week?

Best,
Sean

On Jan 11, 2019, at 08:17, Sean Moss-Pultz <sean@bitmark.com> wrote:

> Hi Noah
>
> Following up from our talk. Here’s some numbers:
>
> - Total yield per day in last quarter = (transfer per day in last quarter) * (0.002 LTC) = 0.0132 LTC
> - Total money won = (total transfers since blockchain launch) * (0.002 LTC) = 6.48 LTC
>
> Where these come from:
>
> - The average is about 60,000 digital properties created each month. 
> - Only 250 properties are transferred each month.
>
> Is that enough to help you think about possible incentives?
>
> Best,
> Sean 
>
>
>
> On Dec 28, 2018, at 09:43, Noah S. Jessop <nsjessop@gmail.com> wrote:
>
>> great - give me a ring when you free up and enjoy surfing!
>> i'm on ET but should be around all day
>>
>> Sent via Superhuman
>>
>>
>> On Fri, Dec 28, 2018 at 10:21 AM, Sean Moss-Pultz <sean@bitmark.com> wrote:
>>
>>     Noah could later this morning work? I’m free after 10:00 AM PST (surfing before that 😬).
>>
>>     Also good in the afternoon if that’s best for you. Or the weekend. 
>>
>>     Sean
>>
>>
>>     On Dec 27, 2018, at 14:59, Noah S. Jessop <nsjessop@gmail.com> wrote:
>>
>>>         Could I pick your brain on how to making Bitmark exciting to mine? 
>>>
>>>     Absolutely. Sorry to be slow on the draw - had a deal close on the 24th and just getting caught up now. Am on ET, let me know when might work well / feel free to try me directly on facetime audio or similar. 
>>>
>>>         For 3: We treat each block in our blockchain as a property; fees are paid to the block owner. This should have the following incentives:
>>>
>>>             The more records a miner includes in their block, the more potential money they can earn in the future
>>>
>>>     I confess for 3, not sure I fully understand what "mining" incentives mean. Is this confirming new blocks? Or acting as the conduit / auto escrow? 
>>>
>>>     Two main things that I see get folks excited - 
>>>     1) more productivity for their equipment
>>>     2) earning interest-like returns
>>>     Either of these should do pretty well in the market itself. 
>>>     You can kind of stand up 1) by doing merge mine / letting people do other things if your work isn't too intensive - i.e. layering in more earnings on top of existing mining stack.
>>>
>>>     ...at any rate, happy to discuss at much more length soon!
>>>
>>>     -Noah
>>>
>>>
>>>
>>>
>>>
>>>
>>>
>>>     Sent via Superhuman
>>>
>>>
>>>     On Sun, Dec 23, 2018 at 7:23 AM, Sean Moss-Pultz <sean@bitmark.com> wrote:
>>>
>>>         Hi Noah
>>>
>>>         One of our goals next year is to work on incentives to mine the Bitmark blockchain. If you had some downtime over the holidays, Could I pick your brain on how to making Bitmark exciting to mine? 
>>>          
>>>         Here is some background...
>>>
>>>         When we architected the Bitmark blockchain we made a conscious decision not to create our own cryptocurrency. We used bitcoin or litecoin for fees. The engineers tried to balance three goals:
>>>
>>>             Let new users create a single digital property (issue records) for free,
>>>             Additional copies of that property (Bitmark certificates records), or ownership transfers (Transfer records) require fees,
>>>             Create an incentive to mine.
>>>
>>>         For 1: We use a proof-of-work (hashcash), included with each issue record, as a “fee” to create digital property. For 2: We use bitcoin or litecoin currently. (It’s easy for us to add more). 
>>>
>>>         For 3: We treat each block in our blockchain as a property; fees are paid to the block owner. This should have the following incentives:
>>>
>>>             The more records a miner includes in their block, the more potential money they can earn in the future
>>>             Miners can sell ownership of their block for immediate money
>>>             Buyers and sellers get purchase protection because the miner provides automated escrow
>>>
>>>         Let me know if anything is unclear. 
>>>
>>>         Best,
>>>         Sean
>>
>>
```