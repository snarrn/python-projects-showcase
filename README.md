# Python Projects Showcase
This repository showcases some of Nathan Snarr's many Python projects that he has worked on for his own learning and enjoyment. These projects are related to concepts in math, cryptography, simulation, machine learning, and more. Summaries of each project are shown below.
> There are currently very few project summaries. More are coming soon.

## Table of Contents
* [Projects](#projects)
    * [Sierpinski Triangle](#sierpinski-triangle)

* [License](#license)

## Projects

### Sierpinski Triangle
I read about an interesting algorithm used to generate the Sierpinski triangle, and I wanted to try it out for myself. The algorithm is as follows:
* Create an image and fill it with a solid background color.
* Define the coordinates of three vertices of an equilateral triangle.
* Randomly select one of the vertices as the current point. This current point is allowed to have fractional coordinates.
* Perform the following for many iterations (thousands, for example):
    * Randomly select a vertex and move the current point exactly halfway toward it.
    * Color the nearest pixel to the current point.
* Save the resulting image.

This is an inefficient way to generate an image of the Sierpinski triangle. Furthermore, the resulting image may have pixel gaps if not enough iterations are used. See the following images, rendered with a 500 x 500-pixel resolution. The first image was generated using 20,000 iterations, and the second image was generated using 100,000 iterations.

![Sierpinski triangle rendered with 20,000 iterations](<sierpinski_triangle/Sierpinski_500x500_20000_Iters.png>)
![Sierpinski triangle rendered with 100,000 iterations](<sierpinski_triangle/Sierpinski_500x500_100000_Iters.png>)

I saw a rendering online in which the triangle was divided into three regions of different colors. A similar rendering can be made by associating each of the triangle's vertices with a color. When the current point moves toward a vertex, the nearest pixel is colored with the color associated with that vertex. The following image shows the result.

![Sierpinski triangle rendered with red, blue, and green regions](<sierpinski_triangle/Sierpinski_500x500_Colored.png>)

I wondered what would happen if a different number and arrangement of vertices were used, such as those defined by a hexagon or octagon. I experimented with different shapes and found the hexagon to be the most interesting. I also tried adding small numbers to each pixel's RGB values instead of setting the pixels to specific colors. For example, if the current point moves toward a particular vertex, then the nearest pixel's red-channel value is incremented by 1 (unless it is already at 255). This allowed colors to mix. The brightness of each pixel also reflects how many times the current point changed its color. The results are shown below.

![Hexagon fractal rendered using relatively few iterations for a speckled effect](<sierpinski_triangle/Sierpinski_Hexagon_Speckled.png>)

![Hexagon fractal rendered using many iterations to produce smooth and detailed coloring](<sierpinski_triangle/Sierpinski_Hexagon.png>)

This algorithm has the benefit of being more general than some other methods of rendering the Sierpinski triangle. It may be configured with unique color schemes and is capable of generating fractals based on various arrangements and numbers of vertices. I learned to use the Python Imaging Library (PIL) to create and edit images. I have used some of these renderings as backgrounds or profile images.

## License
This project is licensed under the Creative Commons Attribution 4.0 International License (CC BY 4.0). See [LICENSE.txt](LICENSE.txt) for details.