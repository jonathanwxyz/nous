#### Is Otsu’s method successful in thresholding all the images?
Otsu's method fails at discerning the blood vessels in the fundus image.
![[Pasted image 20230323165347.png|200]] ![[Pasted image 20230323165450.png|200]]

Otsu's method also fails at discerning in the glaucoma image, the diffuse bright region towards the middle and brighter area inside it.
![[Pasted image 20230323164930.png|200]] ![[glaucoma.jpg|200]]

Otsu's method succeeds in processing the optic nerve head image by highlighting the large, slightly bright area and the smaller brighter area inside it.
![[Pasted image 20230323165732.png|200]] ![[optic nerve head.jpg|200]]

Otsu's method succeeds in discerning the road signs in the motorway image, and the text is clear white.
![[Pasted image 20230323165643.png|200]] ![[motorway.png|200]]

#### How would you modify the thresholding algorithm to address any problems?
I would crop out any black borders in the image in order to reduce the contrast in the image, this would allow the algorithm to discern more subtle changes in colour. The high contrast in some of the images above due to the black borders around the images lead the algorithm into thinking it has found the threshold by simply outlining the border.

Alternatively, one could adopt the binary threshold algorithm and let a human interactively change the threshold value until the desired output is reached.

#### What metrics are there for assessing the success of thresholding?
One way to assess the success of the thresholding is to get humans to do draw a threshold by hand and compare the result to what the machine produced. If the images are similar then the thresholding algorithm is successful. To get a numeric metric we could compare the percentage of pixels that are the same colour.
