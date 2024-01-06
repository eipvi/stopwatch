![stopwatchh](https://github.com/eipvi/stopwatch/assets/87573675/80e0681a-16ef-4c31-a0c7-559816c43c30)

# Stopwatch 

Stopwatch for precise time interval measurement, commonly used in activities such as sports, racing, laboratories, kitchen, and other situations where it is necessary to measure time.

# Technologies used

- JavaScript
- HTML
- Sass

# Primary functions

- The variables store the hours, minutes, and seconds.

```
var hh = 0;
var mm = 0;
var ss = 0;
```
- The variable "time" defines the interval in milliseconds for the setInterval function, which controls the update frequency of the timer. "cron" is a variable that will store the reference to the interval, allowing it to be later stopped with clearInterval.

```
var time = 1000; // Milésimos por 1 segundo
var cron;

```
- The "start" function initiates the timer using setInterval, which calls the "timer" function at each interval defined by the "time" variable.

```
function pause() {
    clearInterval(cron);
}
```

- The "stop" function halts the timer, resets the time variables, and updates the display to reset the counter to '00:00:00' on the interface.

```
function stop() {
    clearInterval(cron);
    hh = 0;
    mm = 0;
    ss = 0;
    document.getElementById('counter').innerText = '00:00:00';
}

```

- The "timer" function is called at regular intervals by setInterval. It increments the seconds, minutes, and hours, formats them into a string in the 'HH:MM:SS' format, and updates the content of the div with the id 'counter'.

```
function timer() {
    ss++;
    if (ss == 60) {
        ss = 0;
        mm++;
        if (mm == 60) {
            mm = 0;
            hh++;
        }
    }
    var format = (hh < 10 ? '0' + hh : hh) + ':' + (mm < 10 ? '0' + mm : mm) + ':' + (ss < 10 ? '0' + ss : ss);
    document.getElementById('counter').innerText = format;
}

```

### Deploy: https://eipvi.github.io/stopwatch/
