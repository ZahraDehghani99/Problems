On mac the default setting of firefox is not appropriate as it shows text and icons extremely little. In order to fix this problem we should go through these steps:

1. Type in the address bar:   about:config 
2. Search for:   layout.css.devPixelsPerPx 
3. If it is not -1.0, then you changed it manually.

The default value is -1, but for mac the appropriate value is 2.2

If you want to use MSC 22 inch as external monitor then this values will cause problem, making firefox overzoom. In order to fix that, we should follow the steps we mentioned previously, only set the value to 1.2
