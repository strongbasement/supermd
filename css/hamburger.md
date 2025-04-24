#### styles to note  for hamburger menu

``` css


/* for bars */

.bar
{
    width:27px;
    height: 2px;
    background-color: white;
    margin: 5px 0px;
transition: all 0.2s ease-in-out;
}

```

#### styles to note  for hamburger menu opening


``` css


.hamburgeropening .bar:nth-child(1){
    transform: translateY(7px) rotate(45deg);
}
.hamburgeropening .bar:nth-child(2){
   opacity: 0;
}
.hamburgeropening .bar:nth-child(3){
    transform: translateY(-7px) rotate(-45deg);
}


```
