# C++

### STL & Pointers

Say we have a class called Event. Which declares `operator <()`. We could use it in a container with sort. However,
if we have `Event*` in a container, we don't get the same sorting behaviour.

We need to use external comparators in order to get the desired behaviour. See [gist](https://gist.github.com/norubai/a896a890825fd4f942e636636cd360af).