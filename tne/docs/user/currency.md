# TNE Currency System

## About
TNE uses a currency system based off of real-world style currency systems. In order to understand the currency system, there's a few key concepts that must be understood.

**Denomination**

Denominations refer to currency tiers. In essence, it's just a currency amount, usually a coin/banknote. For instance, this could be a penny, or $1 bill in the Dollar
currency system in the United States. In Minecraft terms, if we use an item-based gold system for reference, a Gold Ingot and Gold Block would be classified as denominations.

**Currency File Structure**

In TNE, currencies have a fairly straightforward file system, but it has some strict rules to follow. We will dissect the default "USD" structure for example purposes. For this,
we will use the follow image.

![currency directory](https://i.imgur.com/CaD66Xh.png)

Use the following tabs to learn about the different circled key parts of the graphic above.

=== "1"

    The currency file itself, this is where the main configurations surrounding the currency are kept. Please note: no denomination configurations are kept here.

=== "2"

    The currency directory. This is the directory that should hold the denomination files.

=== "3"

    The directory where TNE expects the currency configurations to be. The path is plugin directory/TheNewEconomy/currency.