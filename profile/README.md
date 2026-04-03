<p align="center">
  <img src="https://raw.githubusercontent.com/slop-o-meter/slop-o-meter/main/docs/media/banner.avif" alt="Can We Measure Software Slop?" width="100%" />
</p>

An experiment with questionable results.

## The Idea

Slop is all about **human attention**. LLM-generated code is slop when no person
owns it, understands it, and has verified it works.

If we can quantify how much attention a given piece of software needs
(**attention cost**), and measure how much attention it received (**attention
spent**), we can calculate how "sloppy" it is.

## The Scale

| Score |                                                                                         | Name                    | Description                       |
| :---: | :-------------------------------------------------------------------------------------: | ----------------------- | --------------------------------- |
|   1   |    <img src="https://raw.githubusercontent.com/slop-o-meter/slop-o-meter/main/docs/media/1.buttered-noodles.png" alt="Buttered Noodles" width="64" />    | **Buttered Noodles**    | Slop? Too dated to have any.      |
|   2   | <img src="https://raw.githubusercontent.com/slop-o-meter/slop-o-meter/main/docs/media/2.spaghetti-bolognese.png" alt="Spaghetti Bolognese" width="64" /> | **Spaghetti Bolognese** | A little sauce never hurt.        |
|   3   |             <img src="https://raw.githubusercontent.com/slop-o-meter/slop-o-meter/main/docs/media/3.lasagna.png" alt="Lasagna" width="64" />             | **Lasagna**             | Lots of slop, but with structure. |
|   4   |          <img src="https://raw.githubusercontent.com/slop-o-meter/slop-o-meter/main/docs/media/4.sloppy-joe.png" alt="Sloppy Joe" width="64" />          | **Sloppy Joe**          | Containment is just pretense.     |
|   5   |       <img src="https://raw.githubusercontent.com/slop-o-meter/slop-o-meter/main/docs/media/5.just-the-slop.png" alt="Just The Slop" width="64" />       | **Just The Slop**       | Pure. Proud. Let it flow.         |

## The Algorithm

We use a project's git history to estimate the two attention quantities above,
looking at the size of commits, their distribution, and at the engagement of
their authors. A week-by-week slop score on a scale from 0 to 5 is then
calculated from the estimates.

Weeks that see significant amounts of code added, with disproportionately little
human activity, increase the sloppiness of the project. Weeks with high human
activity and few (or negative) code additions reduce it.

## The Results

Not very good.

They're hit and miss: for some repos they're plausible, but for others they're
just nonsensical.

Setup peculiarities (like vendoring in dependencies) or workflow extravaganzas
(like behind-doors development with periodic code drops) can throw the estimates
completely off.

The measures we're using seem to be a little too indirect. The algorithm needs
more work.

## How Would _You_ Measure Slop?

Wanna take a stab at a better algorithm? Open a PR, and you'll get (pending
approval) a preview environment where you can test your theories.
