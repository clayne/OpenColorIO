..
  SPDX-License-Identifier: CC-BY-4.0
  Copyright Contributors to the OpenColorIO Project.
  Do not edit! This file was automatically generated by share/docs/frozendoc.py.

.. py:class:: CDLTransform
   :module: PyOpenColorIO
   :canonical: PyOpenColorIO.CDLTransform

   An implementation of the ASC Color Decision List (CDL), based on the ASC v1.2 specification.

   **ASC_SOP**

   Slope, offset, power:: out = clamp( (in * slope) + offset ) ^ power

   .. note::
      ​ If the config version is 1, negative values are clamped if the power is not 1.0. For config version 2 and higher, the negative handling is controlled by the CDL style.


   .. py:method:: CDLTransform.CreateFromFile(src: str, id: str) -> PyOpenColorIO.CDLTransform
      :module: PyOpenColorIO
      :staticmethod:

      Load the CDL from the src .cdl, .cc, or .ccc file.

      .. note::
         The cccid can be the ID of a CDL or the index of the CDL (as string). If cccid is NULL or empty the first CDL is returned. The cccid is case-sensitive. The src must be an absolute path reference, no relative directory or envvar resolution is performed. Throws if file does not contain any CDL or if the specified cccid is not found.


   .. py:method:: CDLTransform.CreateGroupFromFile(src: str) -> PyOpenColorIO.GroupTransform
      :module: PyOpenColorIO
      :staticmethod:

      Load all of the CDLs in a .cdl or .ccc file into a single :ref:`GroupTransform`.

      .. note::
         This may be useful as a quicker way for applications to check the contents of each of the CDLs. The src must be an absolute path reference, no relative directory or envvar resolution is performed.


   .. py:method:: CDLTransform.__init__(*args, **kwargs)
      :module: PyOpenColorIO

      Overloaded function.

      1. __init__(self: PyOpenColorIO.CDLTransform) -> None

      2. __init__(self: PyOpenColorIO.CDLTransform, direction: PyOpenColorIO.TransformDirection = <TransformDirection.TRANSFORM_DIR_FORWARD: 0>) -> None

      3. __init__(self: PyOpenColorIO.CDLTransform, slope: Annotated[list[float], FixedSize(3)] = [1.0, 1.0, 1.0], offset: Annotated[list[float], FixedSize(3)] = [0.0, 0.0, 0.0], power: Annotated[list[float], FixedSize(3)] = [1.0, 1.0, 1.0], sat: float = 1.0, id: str = '', description: str = '', direction: PyOpenColorIO.TransformDirection = <TransformDirection.TRANSFORM_DIR_FORWARD: 0>) -> None


   .. py:method:: CDLTransform.equals(self: PyOpenColorIO.CDLTransform, other: PyOpenColorIO.CDLTransform) -> bool
      :module: PyOpenColorIO


   .. py:method:: CDLTransform.getDirection(self: PyOpenColorIO.Transform) -> PyOpenColorIO.TransformDirection
      :module: PyOpenColorIO


   .. py:method:: CDLTransform.getFirstSOPDescription(self: PyOpenColorIO.CDLTransform) -> str
      :module: PyOpenColorIO


   .. py:method:: CDLTransform.getFormatMetadata(self: PyOpenColorIO.CDLTransform) -> PyOpenColorIO.FormatMetadata
      :module: PyOpenColorIO


   .. py:method:: CDLTransform.getID(self: PyOpenColorIO.CDLTransform) -> str
      :module: PyOpenColorIO

      The get/setID methods are now deprecated. The preferred way of interacting with the ID is now via the transform's formatMetadata.


   .. py:method:: CDLTransform.getOffset(self: PyOpenColorIO.CDLTransform) -> Annotated[list[float], FixedSize(3)]
      :module: PyOpenColorIO


   .. py:method:: CDLTransform.getPower(self: PyOpenColorIO.CDLTransform) -> Annotated[list[float], FixedSize(3)]
      :module: PyOpenColorIO


   .. py:method:: CDLTransform.getSOP(self: PyOpenColorIO.CDLTransform) -> Annotated[list[float], FixedSize(9)]
      :module: PyOpenColorIO


   .. py:method:: CDLTransform.getSat(self: PyOpenColorIO.CDLTransform) -> float
      :module: PyOpenColorIO


   .. py:method:: CDLTransform.getSatLumaCoefs(self: PyOpenColorIO.CDLTransform) -> Annotated[list[float], FixedSize(3)]
      :module: PyOpenColorIO

      These are hard-coded, by spec, to r709.


   .. py:method:: CDLTransform.getSlope(self: PyOpenColorIO.CDLTransform) -> Annotated[list[float], FixedSize(3)]
      :module: PyOpenColorIO


   .. py:method:: CDLTransform.getStyle(self: PyOpenColorIO.CDLTransform) -> PyOpenColorIO.CDLStyle
      :module: PyOpenColorIO


   .. py:method:: CDLTransform.getTransformType(self: PyOpenColorIO.Transform) -> PyOpenColorIO.TransformType
      :module: PyOpenColorIO


   .. py:method:: CDLTransform.setDirection(self: PyOpenColorIO.Transform, direction: PyOpenColorIO.TransformDirection) -> None
      :module: PyOpenColorIO

      Note that this only affects the evaluation and not the values stored in the object.


   .. py:method:: CDLTransform.setFirstSOPDescription(self: PyOpenColorIO.CDLTransform, description: str) -> None
      :module: PyOpenColorIO


   .. py:method:: CDLTransform.setID(self: PyOpenColorIO.CDLTransform, id: str) -> None
      :module: PyOpenColorIO


   .. py:method:: CDLTransform.setOffset(self: PyOpenColorIO.CDLTransform, rgb: Annotated[list[float], FixedSize(3)]) -> None
      :module: PyOpenColorIO


   .. py:method:: CDLTransform.setPower(self: PyOpenColorIO.CDLTransform, rgb: Annotated[list[float], FixedSize(3)]) -> None
      :module: PyOpenColorIO


   .. py:method:: CDLTransform.setSOP(self: PyOpenColorIO.CDLTransform, vec9: Annotated[list[float], FixedSize(9)]) -> None
      :module: PyOpenColorIO


   .. py:method:: CDLTransform.setSat(self: PyOpenColorIO.CDLTransform, sat: float) -> None
      :module: PyOpenColorIO


   .. py:method:: CDLTransform.setSlope(self: PyOpenColorIO.CDLTransform, rgb: Annotated[list[float], FixedSize(3)]) -> None
      :module: PyOpenColorIO


   .. py:method:: CDLTransform.setStyle(self: PyOpenColorIO.CDLTransform, style: PyOpenColorIO.CDLStyle) -> None
      :module: PyOpenColorIO

      Use CDL_ASC to clamp values to [0,1] per the ASC spec. Use NO_CLAMP to never clamp values (regardless of whether power is 1.0). The NO_CLAMP option passes negatives through unchanged (like the NEGATIVE_PASS_THRU style of :ref:`ExponentTransform`). The default style is CDL_NO_CLAMP.


   .. py:method:: CDLTransform.validate(self: PyOpenColorIO.Transform) -> None
      :module: PyOpenColorIO

      Will throw if data is not valid.

