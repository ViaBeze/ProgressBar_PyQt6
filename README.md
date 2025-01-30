ProgressBar_PyQt6
Fixed standard PyQt6 ProgressBar 


There was a problem with ProgressBar PyQt6, apparently with Qt in general. When the chunk is small, it goes beyond the edges of the border. A custom class was written that solves this problem.<br>

There was:
![image](https://github.com/user-attachments/assets/48e709b2-7a4f-48d3-89f4-cfebe604288a)
<br>
<br>

It became:
![image](https://github.com/user-attachments/assets/a567ecc2-e0a2-42ab-99ad-dfe8d0b62e8e)



<br>
How to modify to suit yourself:<br>
self._minimum = 0 <-- set minimum value
self._maximum = 500 <-- set maximum value
<br>
    
So you can set fixed or minimal size:<br>
self.setMinimumWidth(500)
self.setMinimumHeight(28)
<br>

I'm not sure if it's what I think it is, but the first parameter is width (don't know max or what, play around), the second parameter is height. Apparently passing -1 means matching {self.setMinimumWidth(500) ; self.setMinimumHeight(28)}, idk. Code:<br>
def sizeHint(self):<br>
    return QSize(-1, 28)
<br>

Example of use:<br>
progress_bar = RoundedProgressBar()

layout.addWidget(progress_bar)
<br>
Usage is actually very simple, which is something I'm proud of.<br>
I wish everyone success;)
