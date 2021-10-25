# Robot bounded in circle
## https://leetcode.com/problems/robot-bounded-in-circle


# Implementation 1 :
```java
class Solution {
    public boolean isRobotBounded(String instructions) {
        int dirX = 0;
        int dirY = 1;
        int x = 0;
        int y = 0;
        for(char ch : instructions.toCharArray()) {
            if(ch == 'G') {
                x += dirX;
                y += dirY;
            } else if(ch == 'L') {
                int tmp = dirY;
                dirY = dirX;
                dirX = tmp * -1;
            } else {
                int tmp = dirX;
                dirX = dirY;
                dirY = tmp * -1;
            }
        }
        // if either we reached to starting cell (0,0) or direction is changed after one iteration, it means
        // robot will fall in cycle
        
        if( (x == 0 && y == 0) || !(dirX == 0 && dirY == 1))
            return true;
        return false;
    }
}
```

## References :
https://www.youtube.com/watch?v=nKv2LnC_g6E (Good explanation)
