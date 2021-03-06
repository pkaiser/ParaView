SET (TESTS_WITHOUT_BASELINES
  ${CMAKE_CURRENT_SOURCE_DIR}/AboutDialog.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/OpenHelp.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/ServerConnectDialog.xml
)

if (PARAVIEW_ENABLE_PYTHON)
  set (TESTS_WITHOUT_BASELINES
    ${TESTS_WITHOUT_BASELINES}
    ${CMAKE_CURRENT_SOURCE_DIR}/TestPythonConsole.xml)
endif()

SET (TESTS_WITH_INLINE_COMPARES
  ${CMAKE_CURRENT_SOURCE_DIR}/Contour.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/DisconnectAndSaveAnimation.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/FileSeries.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/LoadStateMultiView.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/LogColorMap.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/MemoryInspectorPanel.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/NonlinearSubdivisionDisplay.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/RenderNan.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/SaveLargeScreenshot.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/SLACTools.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/TestIsoVolume.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/UpdateTransferFunctionRanges.xml
)

SET (TESTS_WITH_BASELINES)
if(NOT PARAVIEW_USE_VISITBRIDGE)
  # Analyze reader test was conflicting with the reader from VisIt. So
  # disabling it.
  SET (TESTS_WITH_BASELINES ${TESTS_WITH_BASELINES}
    ${CMAKE_CURRENT_SOURCE_DIR}/AnalyzeReaderWriterPlugin.xml)
else()
  SET (TESTS_WITH_BASELINES ${TESTS_WITH_BASELINES}
    ${CMAKE_CURRENT_SOURCE_DIR}/VisItBridgeChombo.xml
    ${CMAKE_CURRENT_SOURCE_DIR}/VisItBridgeEnzo.xml
    ${CMAKE_CURRENT_SOURCE_DIR}/VisItBridgeLAMMPSDump.xml
    ${CMAKE_CURRENT_SOURCE_DIR}/VisItBridgeLAMMPSDump2.xml
    ${CMAKE_CURRENT_SOURCE_DIR}/VisItBridgeNas.xml
    ${CMAKE_CURRENT_SOURCE_DIR}/VisItBridgeNek.xml
    ${CMAKE_CURRENT_SOURCE_DIR}/VisItBridgePdb.xml
    ${CMAKE_CURRENT_SOURCE_DIR}/VisItBridgePFLOTRAN.xml
    ${CMAKE_CURRENT_SOURCE_DIR}/VisItBridgePixie.xml
    ${CMAKE_CURRENT_SOURCE_DIR}/VisItBridgeSamrai.xml)
endif()

if(Module_vtkIOXdmf2)
  SET (TESTS_WITH_BASELINES ${TESTS_WITH_BASELINES}
    ${CMAKE_CURRENT_SOURCE_DIR}/XdmfRead.xml
    ${CMAKE_CURRENT_SOURCE_DIR}/XdmfReadImageData.xml
    ${CMAKE_CURRENT_SOURCE_DIR}/XdmfReadImageDataCollection.xml
    ${CMAKE_CURRENT_SOURCE_DIR}/XdmfReadRectilinearGrid.xml
    ${CMAKE_CURRENT_SOURCE_DIR}/XdmfReadRectilinearGridCollection.xml
    ${CMAKE_CURRENT_SOURCE_DIR}/XdmfReadStructuredGrid.xml
    ${CMAKE_CURRENT_SOURCE_DIR}/XdmfReadStructuredGridCollection.xml
    ${CMAKE_CURRENT_SOURCE_DIR}/XdmfGridAttributes.xml
    ${CMAKE_CURRENT_SOURCE_DIR}/ZLibXDMF.xml
    )
endif()

SET (TESTS_WITH_BASELINES
  ${TESTS_WITH_BASELINES}
  ${CMAKE_CURRENT_SOURCE_DIR}/CTHAMRBaseline.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/CTHAMRContour.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/CTHAMRDualClip.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/CTHAMRClip.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/CTHAMRMaterialInterfaceFilter.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/CTHDerivedDensity2DClyinder.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/AnimatePipelineTime.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/3DWidgetInCustomFilter.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/CalcParens.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/Calculator.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/CameraLink.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/ChartAxisRangeAndLabels.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/Clip.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/ColorEditorControls.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/ColorEditorVolumeControls.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/CategoricalColors.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/ComparativeVisPanel.xml
  # disabling overlay test for now. It has issues with Time 0.
  #  ${CMAKE_CURRENT_SOURCE_DIR}/ComparativeOverlay.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/CompositeSurfaceSelection.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/CreateDelete.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/CustomFilter.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/CustomSourceProbe.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/DataOutlines.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/D3SmallCells.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/DualSphereAnimation.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/EnSight.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/ExodusModeShapes.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/ExodusXML.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/ExportX3dPOVVRML.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/ExTimeseries.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/ExTimeseries2.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/ExtractBlock.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/ExtractLevel.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/FFTOverTime.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/Flow.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/Flow2.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/Fractal2D.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/GlobalProperties.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/GridConnectivity.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/H5PartReaderPlugin.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/LoadPlugins.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/LoadSaveStateAnimation.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/LoadState.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/MultiBlockAttributes1.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/MultiSliceMultiBlock.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/MultiSliceWavelet.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/NormalGlyphs.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/NiftiReaderWriterPlugin.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/OpenSaveData.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/Plot3DReader.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/PlotEdges.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/PlotEdges2.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/PolygonCellSelection.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/PolygonPointSelection.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/ProbePicking.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/PropertyConversion.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/PropertyConversion1.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/PropertyConversion2.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/PropertyConversion3.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/PropertyLink.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/ReadXMLPolyDataFileSeries.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/RectilinearFractal.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/RepresentationSelector.xml

#  ${CMAKE_CURRENT_SOURCE_DIR}/SaveAnimationGeometry.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/SaveColorMap.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/SaveCSV.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/SelectionLabels.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/SelectReader.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/SimpleInteraction.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/Slice.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/SpreadSheet1.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/SpreadSheet2.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/SPTimeseries.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/SpyPlotHistoryReader.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/StreamTracerUpdates.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/StructuredGridVolumeRendering.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/TabbedViews.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/TemporalInterpolator.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/TemporalShiftScale.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/Tessellate.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/Threshold.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/UndoRedo.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/UndoRedo1.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/UndoRedo2.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/UndoRedo3.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/UndoRedo5.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/UndoRedo6.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/UndoRedo7.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/UndoRedo8.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/UnstructuredOutline.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/VariableSelector.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/VariableSelector1.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/ViewSettingsDialog.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/XYChart.xml
  ${CMAKE_CURRENT_SOURCE_DIR}/XYHistogram.xml
  #  ${CMAKE_CURRENT_SOURCE_DIR}/XYBarChart.xml
)

#------------------------------------------------------------------------------
# Add streaming tests.
# We need to locate smooth.flash since it's not included in the default testing
# datasets.
find_file(smooth_flash NAMES smooth.flash
          DOC "Path to smooth.flash data file."
          NO_DEFAULT_PATH)
mark_as_advanced(smooth_flash)
if (EXISTS "${smooth_flash}" AND PARAVIEW_DATA_ROOT)
  # we configure the file since we need to point to smooth_flash.
  configure_file("${CMAKE_CURRENT_SOURCE_DIR}/AMRStreaming.xml.in"
                 "${CMAKE_CURRENT_BINARY_DIR}/AMRStreaming.xml" @ONLY)
  configure_file("${CMAKE_CURRENT_SOURCE_DIR}/AMRVolumeRendering.xml.in"
                 "${CMAKE_CURRENT_BINARY_DIR}/AMRVolumeRendering.xml" @ONLY)

  set (streaming_tests
    ${CMAKE_CURRENT_BINARY_DIR}/AMRStreaming.xml
    ${CMAKE_CURRENT_BINARY_DIR}/AMRVolumeRendering.xml)
  set(AMRVolumeRendering_BREAK TRUE)

  foreach (tname ${streaming_tests})
    add_pv_test("pv" "_DISABLE_C"
      COMMAND --client ${CLIENT_EXECUTABLE}
              -dr
              --enable-streaming
              --disable-light-kit
              --test-directory=${PARAVIEW_TEST_DIR}
      BASELINE_DIR ${PARAVIEW_DATA_ROOT}/Baseline
      TEST_SCRIPTS ${tname})

    add_pv_test(pvcs "_DISABLE_CS"
      COMMAND
         --server $<TARGET_FILE:pvserver>
         --enable-streaming
         --client ${CLIENT_EXECUTABLE}
         -dr
         --enable-streaming
         --disable-light-kit
         --test-directory=${PARAVIEW_TEST_DIR}
      BASELINE_DIR ${PARAVIEW_DATA_ROOT}/Baseline
      TEST_SCRIPTS ${tname})
  endforeach()
endif()

#------------------------------------------------------------------------------

# Probe picking does not work in render server mode
set(ProbePicking_DISABLE_CRS TRUE)

# only enable find data tests if numpy is available
include("TestNumPy")

IF ("1" STREQUAL ${HAS_NUMPY})
  SET(TESTS_WITH_BASELINES ${TESTS_WITH_BASELINES} ${CMAKE_CURRENT_SOURCE_DIR}/FindDataDialog.xml)
ENDIF ("1" STREQUAL ${HAS_NUMPY})

#------------------------------------------------------------------------------
# These tests run using the old panels.

# GlobalProperties test uses global colors which are not currently supported by
# the new panels.
set (GlobalProperties_USE_OLD_PANELS TRUE)

#------------------------------------------------------------------------------
set (TestPythonConsole_BREAK TRUE)

# Selection is not available in CRS mode
set(MultiSliceWavelet_DISABLE_CRS TRUE)
set(MultiSliceMultiBlock_DISABLE_CRS TRUE)
set(PolygonCellSelection_DISABLE_CRS TRUE)
set(PolygonPointSelection_DISABLE_CRS TRUE)
set(NonlinearSubdivisionDisplay_DISABLE_CRS TRUE)

# These tests should not be run along with those using the new panels
set(3DWidgetInCustomFilter_BREAK TRUE)
set(Threshold_BREAK TRUE)
set(ExodusModeShapes_BREAK TRUE)
set(DataOutlines_BREAK TRUE)

# These tests cannot be run using ctest -j since they are affected by focus
# changed events.
set (AnimatePipelineTime_FORCE_SERIAL TRUE)
set (ProbePicking_FORCE_SERIAL TRUE)
set (PolygonCellSelection_FORCE_SERIAL TRUE)
set (PolygonPointSelection_FORCE_SERIAL TRUE)

# Set properties for CTH tests
set(CTHAMRBaseline_BREAK TRUE)

set(CTHAMRContour_BREAK TRUE)
set(CTHAMRContour_DISABLE_CS TRUE)
set(CTHAMRContour_DISABLE_CRS TRUE)

set(CTHAMRDualClip_BREAK TRUE)
set(CTHAMRDualClip_DISABLE_CS TRUE)
set(CTHAMRDualClip_DISABLE_CRS TRUE)

set(CTHAMRClip_BREAK TRUE)
set(CTHAMRClip_DISABLE_CS TRUE)
set(CTHAMRClip_DISABLE_CRS TRUE)

set(CTHAMRMaterialInterfaceFilter_BREAK TRUE)
set(CTHAMRMaterialInterfaceFilter_DISABLE_CS TRUE)
set(CTHAMRMaterialInterfaceFilter_DISABLE_CRS TRUE)

set (TestIsoVolume_BREAK TRUE)
set (TabbedViews_BREAK TRUE)

# Since this test forces remote-rendering, we run it by itself.
set (StructuredGridVolumeRendering_BREAK TRUE)
set (StructuredGridVolumeRendering_FORCE_SERIAL TRUE)
set (StructuredGridVolumeRendering_DISABLE_CRS TRUE)
  # <-- since volume rendering is not supported in CRS mode.

# Since this test needs selection, disable in CRS mode.
set (SelectionLabels_DISABLE_CRS TRUE)

# Mark tests that change change state considerably requires a restart of the
# test suite when grouping tests together for faster playback.
SET (GlobalProperties_BREAK TRUE)
  # <-- since this changes global colors.
SET (XdmfReadImageData_BREAK TRUE)
  # <-- since this changes light kit.
SET (UndoRedo3_BREAK TRUE)
SET (UndoRedo6_BREAK TRUE)
  # <-- since this changes view settings.
SET (UndoRedo1_BREAK TRUE)
SET (UndoRedo2_BREAK TRUE)
SET (UndoRedo7_BREAK TRUE)
  # <-- since these are just long tests, they result in timeouts.

SET (ViewSettingsDialog_BREAK TRUE)
SET (UnstructuredOutline_BREAK TRUE)
  # <-- since this changes view settings.

set (ColorEditorControls_BREAK TRUE)
set (ColorEditorVolumeControls_BREAK TRUE)
set (UpdateTransferFunctionRanges_BREAK TRUE)
set (GridConnectivity_BREAK TRUE)
set (H5PartReaderPlugin_BREAK TRUE)
SET (PlotEdges2_BREAK TRUE)
SET (PolygonCellSelection_BREAK TRUE)
SET (PolygonPointSelection_BREAK TRUE)
SET (PropertyConversion2_BREAK TRUE)
SET (PropertyConversion3_BREAK TRUE)
set (ReadXMLPolyDataFileSeries_BREAK TRUE)
set (ExodusXML_BREAK TRUE)
SET (ComparativeVisPanel_BREAK TRUE)
SET (ComparativeOverlay_BREAK TRUE)
SET (SpreadSheet1_BREAK TRUE)
SET (SPTimeseries_BREAK TRUE)
SET (XYChart_BREAK TRUE)
SET (XYHistogram_BREAK TRUE)
set (ChartAxisRangeAndLabels_BREAK TRUE)

SET(ExtractLevel_BREAK TRUE)

SET(Fractal2D_BREAK TRUE)

# Add image threshold overrides for tests.
# Generally all tests with wireframes need higher thresholds.
SET (Flow2_THRESHOLD 15)
SET (UndoRedo1_THRESHOLD 15)
SET (UndoRedo4_THRESHOLD 15)

# Since often there are issues with fonts etc.
SET (XYChart_THRESHOLD 150)

SET (XYHistogram_THRESHOLD 60)
set (ChartAxisRangeAndLabels_THRESHOLD 60)

# The color and opacity are often different on different machines.
SET (ColorEditorControls_THRESHOLD 60)
SET (ColorEditorVolumeControls_THRESHOLD 300)

SET (SLACTools_DISABLE_CS TRUE)
SET (SLACTools_DISABLE_CRS TRUE)
SET (SLACTools_BREAK TRUE)
SET(SLACTools_THRESHOLD 20)

# DisconnectAndSaveAnimation is only support in Client-Server mode.
set (DisconnectAndSaveAnimation_DISABLE_C TRUE)
set (DisconnectAndSaveAnimation_DISABLE_CRS TRUE)
set (DisconnectAndSaveAnimation_BREAK TRUE)


# Histogram filter produces different results when running in parallel, so
# disable it.
IF (PARAVIEW_USE_MPI)
  SET (XYHistogram_DISABLE_CS TRUE)
  SET (XYHistogram_DISABLE_CRS TRUE)

  SET (SpreadSheet1_DISABLE_CS TRUE)
  SET (SpreadSheet1_DISABLE_CRS TRUE)

  # The hierchical fractal source is a temporary testing source and it does not
  # create the dataset correctly in parallel. Since it's a testing source, I am
  # just going to disable the test in parallel. We can fix the source when
  # needed.
  SET (RectilinearFractal_DISABLE_CS TRUE)
  SET (RectilinearFractal_DISABLE_CRS TRUE)
ENDIF (PARAVIEW_USE_MPI)

# Composite Surface Selection is currently broken in everything but bultin
SET (CompositeSurfaceSelection_DISABLE_CS TRUE)
SET (CompositeSurfaceSelection_DISABLE_CRS TRUE)

# Clip test has object picking which is not supported in client-render-server
# mode.
SET (Clip_DISABLE_CRS TRUE)


# These Xdmf tests have wireframes, hence the increased thresholds.
SET (XdmfReadImageData_THRESHOLD 20)
SET (XdmfReadRectilinearGrid_THRESHOLD 20)
SET (XdmfReadRectilinearGridCollection_THRESHOLD 20)
SET (XdmfReadStructuredGrid_THRESHOLD 20)
SET (XdmfReadStructuredGridCollection_THRESHOLD 20)
SET (XdmfReadImageDataCollection_THRESHOLD 20)

# This test renders points and they are offsetted a bit differently on
# different platforms so just increase the threshold
SET (SaveCSV_THRESHOLD 40)

# Disable some testing configurations for these tests.

## Disable ClientRenderServer tests for FFTOverTime. This is done since
## selection is not supported in render server mode esp. when number of render
## server processess is not same as the data server processes
SET (FFTOverTime_DISABLE_CRS TRUE)

set (LoadStateMultiView_BREAK TRUE)
set (RenderNan_BREAK TRUE)

# ColorEditorVolumeControls does volume rendering of structrued data which required remote
# rendering in client-serve mode.
SET (ColorEditorVolumeControls_DISABLE_CS TRUE)
SET (ColorEditorVolumeControls_DISABLE_CRS TRUE)

# ViewSettingsDialog uses texture background which is currently supported only
# in local render mode.
SET (ViewSettingsDialog_DISABLE_CS TRUE)
SET (ViewSettingsDialog_DISABLE_CRS TRUE)

# MultiBlockAttributes1 requires selection which doesn't work on pvcrs
SET (MultiBlockAttributes1_DISABLE_CRS TRUE)

# Plugins are only built as shared libraries.
IF (NOT BUILD_SHARED_LIBS)
  SET (AnalyzeReaderWriterPlugin_DISABLE_C TRUE)
  SET (H5PartReaderPlugin_DISABLE_C TRUE)
  SET (LoadPlugins_DISABLE_C TRUE)
  SET (NiftiReaderWriterPlugin_DISABLE_C TRUE)
  SET (SLACTools_DISABLE_C TRUE)
ENDIF (NOT BUILD_SHARED_LIBS)
# There should be a client server specific version of this test.
SET (AnalyzeReaderWriterPlugin_DISABLE_CS TRUE)
SET (H5PartReaderPlugin_DISABLE_CS TRUE)
SET (LoadPlugins_DISABLE_CS TRUE)
SET (NiftiReaderWriterPlugin_DISABLE_CS TRUE)
SET (AnalyzeReaderWriterPlugin_DISABLE_CRS TRUE)
SET (H5PartReaderPlugin_DISABLE_CRS TRUE)
SET (LoadPlugins_DISABLE_CRS TRUE)
SET (NiftiReaderWriterPlugin_DISABLE_CRS TRUE)

# Set image threshold overrides for the tests.
SET(SaveLargeScreenshot_THRESHOLD 10000)

# Make these tests use reverse connection.
SET (CutMulti_REVERSE_CONNECT TRUE)

##########################################################
# List of known incompatible tests for Collaboration
#
#   Contains Undo/Redo actions:
#     - Clip, GlobalProperties, UndoRedo, UndoRedo[1-8]
#
#   Contains Plugin Loading actions:
#     - LoadPlugins, NiftiReaderWriterPlugin, H5PartReaderPlugin
#
#   Does not work in CS or CRS mode
#     - ViewSettingsDialog, RectilinearFractal, NewColorEditor
#
#   Does not work because a disconnection is involved
#     - ExportX3dPOVVRML
#
#   Don't want to support for now
#     - ComparativeVisPanel
#     - LoadSaveStateAnimation: The time get reset by collab
#
#   Timing issues (Works on speedy computer)
#     - 3DWidgetInCustomFilter, CustomFilter
#
##########################################################

OPTION(PARAVIEW_COLLABORATION_TESTING
    "Add Collaboration testing"
    ON)
MARK_AS_ADVANCED(PARAVIEW_COLLABORATION_TESTING)

# The create/delete test was only meant for collaboration
SET (CreateDelete_DISABLE_C TRUE)
SET (CreateDelete_DISABLE_CS TRUE)
SET (CreateDelete_DISABLE_CRS TRUE)

# List of test Enable for collaboration
set (AnimatePipelineTime_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (CalcParens_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (Calculator_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (CameraLink_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (CompositeSurfaceSelection_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
set (Contour_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (ContourRange_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
set (CreateDelete_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (CustomSourceProbe_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (D3SmallCells_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (DualSphereAnimation_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (EnSight_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (ExodusModeShapes_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (ExodusXML_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (ExTimeseries_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (ExTimeseries2_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (ExtractBlock_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (ExtractLevel_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (FindDataDialog_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (FFTOverTime_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (Flow_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (Flow2_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (Fractal2D_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (GridConnectivity_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (NormalGlyphs_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (OpenSaveData_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (Plot3DReader_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (PlotEdges_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (PlotEdges2_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (PropertyConversion_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
set (PropertyConversion1_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
set (PropertyConversion2_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
## disabling since the state file doesn't have view layout and such old state
## files are not currently supported in collaborative mode.
##set (PropertyLink_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (ReadXMLPolyDataFileSeries_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (RepresentationSelector_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (SaveColorMap_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (SaveCSV_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (SelectReader_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (SimpleInteraction_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (Slice_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
set (SpreadSheet1_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (SpreadSheet2_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (SPTimeseries_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (SpyPlotHistoryReader_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (StreamTracerUpdates_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (TemporalInterpolator_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (TemporalShiftScale_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (Tessellate_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (Threshold_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (UnstructuredOutline_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
set (VariableSelector_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
set (VariableSelector1_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
set (XdmfRead_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (XdmfReadImageData_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (XdmfReadImageDataCollection_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (XdmfReadRectilinearGrid_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (XdmfReadRectilinearGridCollection_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (XdmfReadStructuredGrid_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (XdmfReadStructuredGridCollection_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (XdmfGridAttributes_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
#set (XYChart_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})
set (ZLibXDMF_ENABLE_COLLAB ${PARAVIEW_COLLABORATION_TESTING})


set(TESTS_WITH_MULTI_SERVERS_3
  ${CMAKE_CURRENT_SOURCE_DIR}/TestMultiServer3.xml
)

IF (PARAVIEW_DATA_ROOT)
  set (TESTS_WITHOUT_BASELINES
    ${TESTS_WITHOUT_BASELINES}
    ${TESTS_WITH_INLINE_COMPARES})
ENDIF (PARAVIEW_DATA_ROOT)

add_client_tests("pv"
  TEST_SCRIPTS ${TESTS_WITHOUT_BASELINES}
  )

IF (PARAVIEW_DATA_ROOT)
  add_client_tests("pv"
    BASELINE_DIR ${PARAVIEW_DATA_ROOT}/Baseline
    TEST_SCRIPTS ${TESTS_WITH_BASELINES}
  )

  add_client_server_tests("pvcs"
    BASELINE_DIR ${PARAVIEW_DATA_ROOT}/Baseline
    TEST_SCRIPTS ${TESTS_WITH_BASELINES}
  )

  add_client_server_tests("pvcs"
    TEST_SCRIPTS ${TESTS_WITH_INLINE_COMPARES}
  )

  IF (PARAVIEW_CLIENT_RENDER_SERVER_TESTS)
    add_client_render_server_tests("pvcrs"
      BASELINE_DIR ${PARAVIEW_DATA_ROOT}/Baseline
      TEST_SCRIPTS ${TESTS_WITH_BASELINES}
    )

    add_client_render_server_tests("pvcrs"
      TEST_SCRIPTS ${TESTS_WITH_INLINE_COMPARES}
    )
  ENDIF (PARAVIEW_CLIENT_RENDER_SERVER_TESTS)

# TODO: remote rendering tests and reverse connect tests.

  add_multi_client_tests("pvcs-collab"
    BASELINE_DIR ${PARAVIEW_DATA_ROOT}/Baseline
    TEST_SCRIPTS ${TESTS_WITH_BASELINES})

  add_multi_server_tests("pvcs-multi-servers" 3
     BASELINE_DIR ${PARAVIEW_DATA_ROOT}/Baseline
     TEST_SCRIPTS ${TESTS_WITH_MULTI_SERVERS_3})

  add_tile_display_tests("pvcs-tile-display" 2 1
     BASELINE_DIR ${PARAVIEW_DATA_ROOT}/Baseline
     TEST_SCRIPTS ${CMAKE_CURRENT_SOURCE_DIR}/TileDisplayScatterPlot-2x1.xml)

  add_tile_display_tests("pvcs-tile-display" 2 2
     BASELINE_DIR ${PARAVIEW_DATA_ROOT}/Baseline
     TEST_SCRIPTS ${CMAKE_CURRENT_SOURCE_DIR}/TileDisplayScatterPlot-2x2.xml)

  add_tile_display_tests("pvcs-tile-display" 1 2
     BASELINE_DIR ${PARAVIEW_DATA_ROOT}/Baseline
     TEST_SCRIPTS ${CMAKE_CURRENT_SOURCE_DIR}/TileDisplay3DTesting-1x2.xml)

  add_tile_display_tests("pvcs-tile-display" 2 1
     BASELINE_DIR ${PARAVIEW_DATA_ROOT}/Baseline
     TEST_SCRIPTS ${CMAKE_CURRENT_SOURCE_DIR}/TileDisplay3DTesting-2x1.xml)

  add_tile_display_tests("pvcs-tile-display" 2 2
     BASELINE_DIR ${PARAVIEW_DATA_ROOT}/Baseline
     TEST_SCRIPTS ${CMAKE_CURRENT_SOURCE_DIR}/TileDisplay3DTesting-2x2.xml)


  #------------------------------------------------------------------
  # Add tests that test command line arguments (among other things).
  #------------------------------------------------------------------
  if (PARAVIEW_DATA_ROOT)

    # The state file need to point to the correct data file. We do that by
    # configuring the state file.
    configure_file (
      "${CMAKE_CURRENT_SOURCE_DIR}/exodusStateFile.3.14.1.pvsm.in"
      "${CMAKE_CURRENT_BINARY_DIR}/exodusStateFile.3.14.1.pvsm" @ONLY)
    add_pv_test("pv" "_DISABLE_C"
      COMMAND --client $<TARGET_FILE:paraview>
              -dr
              --test-directory=${PARAVIEW_TEST_DIR}
              --state=${CMAKE_CURRENT_BINARY_DIR}/exodusStateFile.3.14.1.pvsm
      BASELINE_DIR ${PARAVIEW_DATA_ROOT}/Baseline
      TEST_SCRIPTS ${CMAKE_CURRENT_SOURCE_DIR}/LoadExodusStateFile.xml)
  endif()

ENDIF (PARAVIEW_DATA_ROOT)
