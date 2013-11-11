#--------------------------------------------------------------------------#
################################### UTIL ###################################
#--------------------------------------------------------------------------#

This directory holds various outdated utility classes, some of which are libraries
used by Recognition and FrontEnd, while others are testing, training, and
analysis libraries.

BayesianRecognizer: Empty, for now.

Classifier: A UI based on the Labeler for testing classification and
	clustering. Currently only used by the team at UCR.

ConverterDRS: DRS file-type handling. Currently read-only.

DataAnalysis: Some very old code that extracts the following statistics from
	labeled sketches:
	   * Number of gates/wires drawn with non-consecutive strokes
	   * Order of text relative to diagram pieces
	   * Order of labels vs. rest of diagram
	   * Order of gates vs. wires that connect to them
	   * Timing between strokes in the same object vs. different objects
	   * Differences between participants in any of the above
	   * Number of strokes per each gate, wire, and text item
	   * Length of strokes in each gate, wire, and text item

DecisionTreeFeatures: Console application for parsing our features
	(primarily those of the CRF) into the C4.5 decision tree file format.
	This was used in Summer 2008 to choose an ideal featureset in
	conjunction with UC Riverside.

GateStudy: Computes statistics on timing and other information for collected
	data and writes them to a CSV file. Written by the mysterious rgordon.

GaussianBlur: A fast implementation of a Gaussian Blur implemented from
	the article "Fast Gaussian Blur Algorithm in C#" found at "Adrian's Tech
	Blog" -- http://www.cnblogs.com/Dah/archive/2007/03/30/694527.html

GenerateSubsets: Get all subsets of a parameterized array, and optionally
	call a function on them. Not used by anything, but could be useful at
	some point in the future.

InkExplorer: A sample application provided with the Microsoft Tablet PC
	Platform SDK for analyzing stroke data. Notable in that it is painfully
	slow.

InkRecognition: A sample application provided with the Microsoft Tablet PC
	Platform SDK which performs text recognition using the Microsoft.Ink
	recognizer

InkToSketch: Used to convert tablet ink from Microsoft.Ink to Sketch.Sketch.
	I'm not sure why this is necessary any more, since the Labeler can read
	JNT files and save them as XML files, and hand-label them along the way.

Labeler: The primary UI used to label and view sketches. For much more
	information, see the REAPlease note that
   autofragmentation will clear any hand-fragmentation that you have
   previously performed.DME file in the Labeler\ directory.

LabelMapper: Used to translate between shape labels in the domain, and
	simplified labels for use with the CRF or equivalent. For more
	information, see the README file in the LabelMapper\ directory.

NeighborhoodMap: Contains several classes:
   * LinkedPoint maps a point to a substroke that it came from
   * NeighborhoodMap is a graph structure describing which substrokes are
     close to which other substrokes
   * Neighborhood: A testing/executable file with hardcoded paths.

Network: Some miscellaneous TCP/IP code that is no longer used by anything.
	Seems to implement a chat server running on port 1234 of machine
	134.173.43.9

PairedList: A list class that stores two items for each entry, and can sort
	by either of them. Quite messy code. 

Pin: Data structure used to store circuit labels and values

SketchCorrectness: compares two labeled sketches to determine how correct
	they are compared to each other

SketchStats: computes stats about a sketch (specifically a truth table) and 
	prints them

SwitchLabels: A deprecated precursor to LabelMapper which is hardcoded to
	convert the labels "AND", "OR", "NOT", "NAND", "NOR", "XOR", and "XNOR" to
	"Gate" in sketch files. Almost certainly no longer needed. Interesting
	note: the author apparently cannot spell "argument".

SwitchTypeName: switches type and name fields in the labeled xml file. Not
	needed any more, but required because some files were created with
	switched fields, and were not compatible with anything.

TestCircuitRec: used to test CircuitRec

TestCongealing: Ad-hoc testing code for the congealing image recognizer (See
	the Recognition\Congeal directory for more information). Largely
	superceded by the integration of Congeal into the Recognizers framework
	and TestRig's SymbolStage.

TestConverter: initially, this was used to test Converter, but now it can
	test a lot of other stuff too

TestRecogntition: Wrapper to test the Microsoft.Ink text recognizer.

TrainingDataPreprocessor: Preprocesses XML files into binary files used to
	train the Congealer (and, theoretically, any other recognizer that
	wanted to implement the required APIs). Vastly reduces training time.
	For more information, see the README file in the
	TrainingDataPreprocessor\ directory

ThresholdEval: Seems to have been designed to find thresholds for the CRF.
	Highly mediocre code. For more information, see the ThresholdEval node
	on twiki.

VerilogWriter: writes recognized circuit to Verilog