# MultiDimMarket
an arbitrarily dimensional market for any limited resource

## idea

each entity that exists is a bundle of energy (E) and info (I)

each entity has input and output streams, both for E and I called i and o
e.g. o_I(x) is the info output stream of x

all streams have a finite bandwidth called bw

an interaction between any 2 entities A and B is an exchange of E and I via the streams:
o_I(A) -> i_I(B)
o_I(B) -> i_I(A)
o_E(A) -> i_E(B)
o_E(B) -> i_E(A)

an interaction is essentially a trade of energy or info
from micro economics, we know that a fair trade is beneficial to both parties

any interaction also costs all involved entities some loss of energy, which is considered equal on all entities

assume a utility function u_A of info from the perspective of A
e.g. u_A(I(B)) is the utility enjoyed by A from consuming the info of B
almost always u_A(I(B)) != u_B(I(A))
wlog, assume u_A(I(B)) > u_B(I(A))
then we call B the host of the interaction (H)
the other entities, like A, are called Guest (G)

due to the above inequality, G needs to offer some energy to make the interaction fair

lets consider an arbitrary entity called H (host) that wants to share their I(H) via o_I(H)
in return, H receives E via i_E(H) ~ this market converges to a fair exchange between o_I(H) and i_E(H)

since bw(o_I(H)) is finite, there is a need to prioritise the G_i

this market concept provides a method to do so whilst
giving every G_i their turn
giving advantage to those offering more E ~ the advantage level is controllable by H with a simple parameter
E can come in any form, including subjectively xor objectively valuable
giving H a full overview of the entire market, even those 

ultimately, H offers I(H) and G_i offer E(G_i)

all E is exchanged as granularly as possible (dt is small, e.g. dt=1sec)

E can be split into 2 types:
objective value <=> liquidly tradable to other forms of E which allows E to be valued: v(E)
subjective value <=> no objective value: v(E) undef

H chooses min value of energy min(H)
this splits E(G_i) into 3 categories:
G_i is a HighRoller <=> min(H) < v(E) 
G_i is a Chrony <=> min(H) == v(E)
G_i is a Lurker <=> v(E) < min(H) // a Lurker never receives I(H), but indicates interest to H, giving H a full market overview, allowing for a fair market price
G_i is an Eccentric <=> v(E) undef

H chooses 3 positive integers as importance for HighRoller (NH), Chrony (NC), Eccentric (NE) such that
on average, amongst NH+NC+NE Guests, NH will be HighRoller, NC will be Chrony, NE will be Eccentric
in practice, H can actually choose 2 decimal values between 0 and 1 to equivilantly represent the same
