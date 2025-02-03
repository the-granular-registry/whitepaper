# How can Renewable Generators Create Positive Emissions (Negative LMEs)?

Negative Locational Marginal Emissions (LMEs) can seem confusing, but they are a part of the complex system of grid management, similar to negative Locational Marginal Prices (LMPs).&#x20;

Typically, when the grid is not experiencing any transmission line congestion and a specific location on the grid requires an incremental unit of electricity, the grid operator will simply disbatch (or redispatch) the lowest cost generator to service the load in need. In this congestion-free scenario, the lowest cost generator able to deliver power to that location is the generator setting the marginal cost of power - and is the genrator setting the marginal emmissions value - at that location. The main takeaway here is this scenario has only one marginal generator.&#x20;

However, when the transmission lines become congested, it isn't possible for grid operators to rely on just the cheapest generators. Instead, multiple marginal generators come into play to avoid overloading the transmission lines. The number of marginal generators equals 1 plus the number of binding transmission constraints. For instance, if there are two binding constraints, there will be three marginal generators. This means that different energy sources, with potentially different emissions factors, might be used to set the marginal emissions value at a location experiencing transmisson congestion.&#x20;

In some instances, renewable projects like wind and solar can lead to negative LMEs; as they have been mixed in with other marginal generators during periods of congestion. For example, a solar project might not only curtail another solar project but also cause an increase in coal plant output on the opposite side of the transmission constraint, leading to a net increase in emissions and hence a negative LME at the project node.

Let's looks at a simple example using three generators and three loads on a triangular grid:

<figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

As mentioned earlier, LMPs and LMEs are determined by the generation redispatch required to maintain supply-demand balance and manage congestion. In the above graph, we can see that there is a binding constraint on Line 2 (RED) which leads to a situation where grid operators need to rely on multiple generators to set the LMPs. Due to this binding constraint, **both** Gen 1 and Gen 2 (BULE) are used to set the marginal unit.

Now Let's see what happens when we increase generation production at Gen 3; which is non-margin generator in this grid  and presumably the renewable generator (remember, Gen 1 and Gen 2 are currently on the margin):

<figure><img src="../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

We can see that Gen 3's injection of 1MW of incremental power directly flows to alleviate the congestion on Line 2. However, now the grid operator has to redisbatch again in this moment to maintain balance. See below:

<figure><img src="../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

The least-cost solution for redispatch in response to an incremental MW from Gen 3 is ramping down Gen 2 by 2 MW (since it is the highest-cost generator @ $10), and ramping up Gen 1 by 1 MW. This maintains balance on the grid via the GREEN and PURPLE flows, but Line 2 remains congested and Gen 3 (the lowest-cost generator) **is not** on the margin.

**Final Clean View and Conclusion:**

<figure><img src="../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

Because multiple units are simultaneously being ramped up and down, you can end up with LMPs that exceed the offer points of any single generator. LMPs and LMEs extend beyond offer curves provided by individual generators. In the example, the 1 MW injection at Gen 3 reduces system cost by $15, despite that being higher than the costs of any individual generator. So, the LMP at the Gen 3 node is $15/MWh. The same thing happens with LMEs, where the LME at Gen 3 is 1 ton/MWh despite that being higher than the emissions rate of the most emitting power plant.

This happens both positively and negatively. We've seen some solar projects, for example, not only curtail other solar projects but also cause a coal plant on the other side of the transmission constraint to increase its output in order to balance the system. The result is a negative LME at the project node, because the generation from the solar plant causes a net increase in emissions. This is fairly rare, and usually brief, but does happen.

Understanding negative Locational Marginal Emissions (LMEs) requires an appreciation of the complexities of grid management and transmission constraints. Just as Locational Marginal Prices (LMPs) can be influenced by multiple generators during periods of congestion, LMEs can similarly reflect the combined impact of various energy sources. The example above demonstrates how renewable projects, such as wind and solar, can lead to negative LMEs by curtailing other renewable sources and inadvertently increasing output from higher-emission generators. This highlights the intricate dynamics of grid operations, where the interplay of transmission constraints and generator redispatch can result in unexpected emissions outcomes. Recognizing these nuances is crucial for optimizing grid performance and advancing sustainable energy solutions.&#x20;

Thankfully, we're here to help you understand these nuances and make the most out of your operations!
