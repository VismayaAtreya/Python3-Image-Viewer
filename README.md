# Python3-Image-Viewer
Of course, all operating systems have image viewers now, but what if you wanted to make your own, with more options? You can fork this repository and make one with more features!

## Explaining the code
Let us start of with the first few lines - Importing the modules

```
1. #Importing
2. from tkinter import *
3. from PIL import ImageTk, Image
4. from tkinter import filedialog
5. from tkinter.messagebox import showinfo
```
* tkinter: As you may know, tkinter is the basic package to make GUI windows and widgets.
* PIL: From PIL, we will be using ImageTk and Image. These are to open the images.
* filedialog: It is a tkinter function that allows you to select a file from a different window.

![alt_text](https://github.com/VismayaAtreya/Python3-Image-Viewer-Base/blob/master/User%20Guide%20Images/1.png)

* showinfo:- It is a tkinter function that allows you to send alerts and messages. It is commonly used in desktop notifiers.
```
6. def next_func():
7.     welcome.destroy()
8.     root = Tk()
9.     root.title('Py Image Viewer')
```
* These four lines make up one of the functions.
* Here,'.destroy' destroys a tkinter window, a way it can never be used again.
* Line 8 creates a new tkinter window called 'root' and line 9 changes the title to 'Py Image Viewer'

```
10.     #Functions
11.     def openfn():
12.         filename = filedialog.askopenfilename(title='Load Image')
13.         return filename
14.     def open_img():
15.         x = openfn()
16.         try:
17.             img = Image.open(x)
18.             width, height = img.size    
19.             img = img.resize((width, height), Image.ANTIALIAS)
20.             root.geometry(str(width)+"x"+str(height))
21.             img = ImageTk.PhotoImage(img)
22.             panel = Label(root, image=img)
23.             panel.image = img
24.             panel.pack()
25.        except:
26.             showinfo("Error", "The file you tried to open was not a supported image file.")
27.             root.destroy()
28.     open_img()
29.     root.mainloop()# mainloop
```
* In line 12, we use the tkinter filedialog and return it in line 13.
* In line 15, you can see the usage of the 'Image' module.
* In line 18, we get the size of the image opened and and set the dimensions of the tkinter window and the image.
* In line 21, ImageTk is used to create the image and it is turned into a label and packd in line 22, 23 and 24.
* If all of this fails, the tkinter 'showinfo' function is used in line 26 and the window is destroyed in line 27.
