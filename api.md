---
layout: default
---

# [](#header-1)API Documentation

We explain the main APIs used in writing the specification and configuring **RGSE**.

## [](#header-2)**Functions for making a variable symbolic**

<p><font color="#0000FF" size="4">makeConcolicInteger("sym_m", "a"):</font> This function will make an integer variable symbolic (denoted as <i>sym_m</i>), and initialize it to the concrete integer value <i>a</i>.</p>

<p><font color="#0000FF" size="4">makeConcolicChar("sym_c", "c"):</font> This function will make a char variable symbolic (denoted as <i>sym_c</i>), and initialize it to the concrete char <i>c</i>.</p>

## [](#header-2)**Function for building the FSA**

<p><font color="#0000FF" size="4">FiniteStateAutomaton getForwardFSA() :</font> This function is used to specify the regular property as a deterministic finite state automaton (FSA).</p>

## [](#header-2)**Functions in class FiniteStateAutomaton**

<p><font color="#0000FF" size="4">(1). FiniteStateAutomaton() :</font> The construction function of the class <i><b> FiniteStateAutomaton </b></i>, and it will return an empty finite state automaton.</p>

<p><font color="#0000FF" size="4">(2). createState(Point p) :</font> Create a state in FSA. The parameter <i>p</i> is a point that specifies a location in the coordinate space.</p>

<p><font color="#0000FF" size="4">(3). addTransition(Transition t) :</font> Add a transition to the FSA, and parameter <i>t</i> is the transition to be added. Specifically, a transition can be constructed by invoking function <i><b>"new FSATransition(s0, s1, "I")"</b></i>, which means executing event <i>I</i> can drive state <i>s0</i> to state <i>s1</i>.</p>

## [](#header-2)**Functions in class MonitorWithDFA**

The functions in class MonitorWithDFA are used to build a Java monitor.

<p><font color="#0000FF" size="4">(1). MonitorWithDFA(FiniteStateAutomaton fsa) :</font> Construct a monitor according to the given FiniteStateAutomaton <i>fsa</i>.</p>

<p><font color="#0000FF" size="4">(2). addSensitiveEvent(String typeName, String methodName) :</font> Suppose the monitor is constructed by an FSA <i>fsa</i>, then this function is used to describe the transition events in <i>fsa</i>. For example, suppose instruction <i>instr</i> is a method call instruction, if the class name of the invoked method equals parameter <i>typeName</i> and the method name equals parameter <i>methodName</i>, then <i>instr</i> is a sensitive event of the regular property.</p>

<p><font color="#0000FF" size="4">(3). addMethodNameChar(String methodName, Char ch) :</font> This function associates a sensitive method named <i>methodName</i> with the transition label <i>ch</i> in the FiniteStateAutomaton <i>fsa</i>. For example, suppose the FiniteStateAutomaton <i>fsa</i> has a transition <i>(s0, s1, "I")</i>, if we invoked <i>addMethodNameChar("init", "I")</i>, then when we encouter a instruction that invoked a method named <i>init</i>, state <i>s0 will be updated to state s1</i>.</p>

## [](#header-2)**Function for initializing arguments.**

<p><font color="#0000FF" size="4">initArgs(String[] args) :</font> This function sets the running configuration. The parameter args is an array with seven string elements, and they represent <i><b>call string bound</b></i>, <i><b>property guided</b></i>, <i><b>refinement flag</b></i>, <i><b>iteration number</b></i>, <i><b>iteration period</b></i>, <i><b>result file name</b></i>, and <i><b>slicing flag</b></i>, respectively. For example, suppose the args equals {"1", "1", "0", "-1", "0,0,100,0","","0"}, then the call string bound is 1, and <b>RGSE</b> will run in the guiding mode with no refinement, no iteration threshold, 100 seconds time threshold (the types of the four elements are hour, minute, second, millisecond, respectively), empty result file, and no slicing.</p>

