..
  SPDX-License-Identifier: CC-BY-4.0
  Copyright Contributors to the OpenColorIO Project.
  Do not edit! This file was automatically generated by share/docs/frozendoc.py.

.. py:class:: GradingToneTransform
   :module: PyOpenColorIO
   :canonical: PyOpenColorIO.GradingToneTransform

   Tonal color correction controls.

   This transform is for making fine adjustments to tone reproduction in specific tonal ranges.

   There are five tonal controls and each one has two parameters to control its range:
   - Blacks (start, width)
   - Shadows(start, pivot)
   - Midtones(center, width)
   - Highlights(start, pivot)
   - Whites(start, width)

   The transform has three styles that adjust the response and default ranges for linear, logarithimic, and video color encodings. The defaults vary based on the style. When the style is linear, the units for start/width/etc. are photographic stops relative to 0.18.

   Each control allows R, G, B adjustments and a Master adjustment.

   There is also an S-contrast control for imparting an S-shape curve.

   The controls are dynamic, so they may be adjusted even after the :ref:`Transform` has been included in a :ref:`Processor`.


   .. py:method:: GradingToneTransform.__init__(*args, **kwargs)
      :module: PyOpenColorIO

      Overloaded function.

      1. __init__(self: PyOpenColorIO.GradingToneTransform, values: PyOpenColorIO.GradingTone, style: PyOpenColorIO.GradingStyle = <GradingStyle.GRADING_LOG: 0>, dynamic: bool = False, dir: PyOpenColorIO.TransformDirection = <TransformDirection.TRANSFORM_DIR_FORWARD: 0>) -> None

      Creates an instance of :ref:`GradingToneTransform`.

      2. __init__(self: PyOpenColorIO.GradingToneTransform, style: PyOpenColorIO.GradingStyle = <GradingStyle.GRADING_LOG: 0>, dynamic: bool = False, dir: PyOpenColorIO.TransformDirection = <TransformDirection.TRANSFORM_DIR_FORWARD: 0>) -> None

      Creates an instance of :ref:`GradingToneTransform`.


   .. py:method:: GradingToneTransform.getDirection(self: PyOpenColorIO.Transform) -> PyOpenColorIO.TransformDirection
      :module: PyOpenColorIO


   .. py:method:: GradingToneTransform.getFormatMetadata(self: PyOpenColorIO.GradingToneTransform) -> PyOpenColorIO.FormatMetadata
      :module: PyOpenColorIO


   .. py:method:: GradingToneTransform.getStyle(self: PyOpenColorIO.GradingToneTransform) -> PyOpenColorIO.GradingStyle
      :module: PyOpenColorIO

      Adjusts the behavior of the transform for log, linear, or video color space encodings.


   .. py:method:: GradingToneTransform.getTransformType(self: PyOpenColorIO.Transform) -> PyOpenColorIO.TransformType
      :module: PyOpenColorIO


   .. py:method:: GradingToneTransform.getValue(self: PyOpenColorIO.GradingToneTransform) -> PyOpenColorIO.GradingTone
      :module: PyOpenColorIO


   .. py:method:: GradingToneTransform.isDynamic(self: PyOpenColorIO.GradingToneTransform) -> bool
      :module: PyOpenColorIO

      Parameters can be made dynamic so the values can be changed through the CPU or GPU processor, but if there are several :ref:`GradingToneTransform` only one can have dynamic parameters.


   .. py:method:: GradingToneTransform.makeDynamic(self: PyOpenColorIO.GradingToneTransform) -> None
      :module: PyOpenColorIO


   .. py:method:: GradingToneTransform.makeNonDynamic(self: PyOpenColorIO.GradingToneTransform) -> None
      :module: PyOpenColorIO


   .. py:method:: GradingToneTransform.setDirection(self: PyOpenColorIO.Transform, direction: PyOpenColorIO.TransformDirection) -> None
      :module: PyOpenColorIO

      Note that this only affects the evaluation and not the values stored in the object.


   .. py:method:: GradingToneTransform.setStyle(self: PyOpenColorIO.GradingToneTransform, style: PyOpenColorIO.GradingStyle) -> None
      :module: PyOpenColorIO

      Will reset value to style's defaults if style is not the current style.


   .. py:method:: GradingToneTransform.setValue(self: PyOpenColorIO.GradingToneTransform, values: PyOpenColorIO.GradingTone) -> None
      :module: PyOpenColorIO


   .. py:method:: GradingToneTransform.validate(self: PyOpenColorIO.Transform) -> None
      :module: PyOpenColorIO

      Will throw if data is not valid.

