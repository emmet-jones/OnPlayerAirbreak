OnPlayerAirbreak
===================

Simple airbreak detection script for SA-MP. Just include it in your mode and you're ready to go!

Function
===================
You can use this function to check and reset a player's airbreaks count.

```
//Example
new airbreaks[MAX_PLAYERS];

public OnGameModeInit()
{
    SetTimerEx("ResetAirbreakCount", 1000, 1, "d", playerid);
    return 1;
}

forward ResetAirbreakCount(playerid);
public ResetAirbreakCount(playerid)
{
    if(!IsPlayerAirbreaking(playerid) && airbreaks[playerid] > 0) airbreaks[playerid]--;
}
```
Callback
===================
There is only one callback included which is called when airbreak is detected.

```
//Example
new airbreaks[MAX_PLAYERS];

public OnPlayerAirbreak(playerid)
{
    airbreaks[playerid]++;
    if(airbreaks[playerid] > 5) Kick(playerid);
}
```

This callback is called when a player is either airbreaking on foot, or in a vehicle.
