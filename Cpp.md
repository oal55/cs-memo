# C++

### STL & Pointers
Say you are using some STL container that uses `sort` with a custom object, such as `std::set`. 

Let us just throw some random object here.
```cpp
#include <set>

using namespace std;

struct event {
    int time, type;
    event(int _time, int _type): time(_time), type(_type) {}
    bool operator <(const event& other) const {
        if (time == other.time)
            return type < other.type;
        return time < other.time;
    }
};
```

And say we have the following two sets.
```cpp
set<event> events;
set<event*> event pointers;
```

```cpp
int main() {
    event mid(10, 2);
    event lo(2, 3);
    event hi(14, 3);

    // insert objects.
    events.insert(mid);
    events.insert(lo);
    events.insert(hi);

    // insert pointers. Just for clarity, there are 6 objects on the stack at this line.
    eventPointers.insert(&mid);
    eventPointers.insert(&lo);
    eventPointers.insert(&hi);

    for (auto &event: events)
        cout << event.time << " ";
    cout << endl;

    for (auto &event: eventPointerst)
        cout << event->time << " ";
    cout << endl;

	return 0;
}
```

Now we insert events to each of those sets.