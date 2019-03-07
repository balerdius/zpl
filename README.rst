zpl
===

Python ZPL2 Library generates ZPL2 code which can be sent to Zebra or similar label printers. The library uses only Millimeter as unit and converts them internally according to printer settings.

Example use
-----------

.. code-block:: python

   from zpl import Label
   from PIL import Image
   import sys

   l = Label(105,75)  //Tamaño de la etiqueta
   //
   //Le pasamos la posicion donde queremos la imagen y su dimension
   //
   posx = int(sys.argv[1])
   posy = int(sys.argv[2])
   sizeh = int(sys.argv[3])
   sizew = int(sys.argv[4])
   
   height = sizeh
   image_width = sizew
   image_height = l.write_graphic(Image.open(sys.argv[5]),image_width)
   l.endorigin()

   
This will display the following preview image, generated using the `Labelary API <http://labelary.com/>`_:
`label preview http://labelary.com/viewer.html `_

The generated ZPL2 code is:

::

   ^FS^FO330,156^GFA,768,384,8,00003FFFC0000000000600000FF0000000180200C01F8000003008000000600000204080440D10000041080000000C000082420000CC020000840002000102000100200001008000010040000000800002000FF80000010006003F84003E01800C036F8200E100C01402307101FE01202878000E030000A071060200010001504201FC0000007C50821000000106C090A438000001800010A466001E0040115084A183C80070103042107009C044382060104E0800803A20300C40E00700F840380FE03C0003D8001A047021F83C588004027E2021845880020227E021047880020141F82187F8800100C07FFFFFF88001004047FFFFF88000803040FFFFF88000C00880419970800060078001117080001241C00012608000089038C237C08000060401FFF8008000011080000020000000C21040E0044000003863C0010840000006060000104000000180380080400000006000000080000000180000008000000007800001000000000038000600000000000380180000000000003FC000^FS
   
Installation
------------
::
    
    pip install --user zpl


Requirements
------------
* PIL or Pillow
