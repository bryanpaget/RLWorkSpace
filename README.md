# RLWorkSpace

## Reinforcement Learning for Smooth Workspace Manifolds

The goal is to train an agent to assign a sane layout to an ever changing 2D array of windows. The domain is $\mathbb{R}^{2}$ and the range is the same. To motivate the need for this consider the following scenario. You are working on your super awesome Linux computer running GNOME and you have few windows open, tiled according to your preferences. Then you create a new window or you destroy one of the existing windows. The windows then have to rearrange themselves according to some fixed algorithm which probably didn't work out the way you wanted so then you move the windows around until you are happy with the layout and continue working.

What RLWorkSpace sets out to do is add an agent to the mix that sees what windows you have open, the data are in the form of a list of application name and coordinates e.g.

    [
        ("Application One", ((3, 4), (6, 8))),
        ("Application Two", ((1, 1), (9, 9))),
        ("Application Three", ((8, 8), (12, 12))),
    ]

The application names are an essential feature since the agent will learn that different applications tend to be relegated to different parts of the screen. For instance, 



User creates or destroys a window. Then there is a slight delay. Then user either accepts or rejects the layout.

If the user rejects the layout they will set the layout to what they want.

The process is:

New Window Created --> Algorithm Assigns Layout --> 

# Data:

 - Application name
 - Coordinates
 - Screen size

## Time period.
    
This will have to be a hyperparameter.

## The World According to the Agent

The agent lives inside of a discrete time world of two dimensions. It watches as named rectangles are created, arranged and destroyed. It wants to learn how to predict the next layout given the existing layout. 

### The Solution the Agent Forever Seeks

The problem has two parts:

  1. Given an existing layout and a new window to add to the layout, how to arrange everything?
  2. Given an existing layout and one newly destroyed window, how to arrange everything?

There are some constraints:
    
  1. It wants to minimize the number of windows moved and the amount of movement for each window that does move.
  2. It wants to retain the given layout and will create sub layouts to keep the layout.

It has a rough set of guidelines that define a layout.


**Definition (Layout):** A Layout is a set of rules defining acceptable boundary behavior for windows.

**Definition ():**

Collect x,y coordinates for windows, for each time step we'll have a list of those, one for each window.

# Methods:

## Assign Layout.

Given the following constraints:

    1. Windows are at least a certain size relative to the monitor size. We don't want to see super tiny windows. But on a smaller screen you'll have to make do.  
    
# Data Collection

## Reporting

I want to be as transparent as possible about the data that is collected, how it is stored and who sees it. Most importantly I want to be clear about what the data is used for. Collected data is used to made the model better, that it all. The data stays on your computer by default. In the settings panel there is an option to enable sharing the data back to me, to increase the size of my training data. No personal information is stored in the data. And only x,y coordinates are being sent.
