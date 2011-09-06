
{
  {

    "with reference to http://www.webcom.com/haahr/dylan/linearization-oopsla96.html"

    var _=require("./clos"),Class=_.Class,_next=_._next;


    "    A    "
    "   / \   "
    "  B   C  "
    "   \ /   "
    "    D    "

    var A=Class.def("A",[],function(supr){return {
      a:10
      name:"Aa",
      log:function(){
        console.log("i'm",this.name,"age",this.a)
        return _next(this,supr.log,arguments)}}})

    var B=Class.def("B",[A],function(supr){return {
      name:"Bb",
      b:20,
      log:function(){
        console.log("i'm",this.name,"age",this.b)
        return _next(this,supr.log,arguments)}}})

    var C=Class.def("C",[A],function(supr){return {
      name:"Cc",
      c:30,
      log:function(){
        console.log("i'm",this.name,"age",this.c)
        return _next(this,supr.log,arguments)}}})

    var D=Class.def("D",[B,C],function(supr){return {
      name:"Dd",
      d:40,
      log:function(){
        console.log("i'm",this.name,"age",this.d)
        return _next(this,supr.log,arguments)}}})

    debugger;
    {
      var a=A.new(),b=B.new(),c=C.new(),d=D.new();
      a.log();
      console.log("-------------");
      b.log();
      console.log("-------------");
      c.log();
      console.log("-------------");
      d.log();
    }

    "              <object>                   "
    "                  |                      "
    "               <boat>                    "
    "               /     \                   "
    "              /       \                  "
    "       <day-boat>   <wheel-boat>         "
    "          /     \     /                  "
    "         /       \   /                   "
    " <engine-less>    \ /                    "
    "        |          X                     "
    "        |         / \                    "
    "        |        /  <small-multihull>    "
    "        |       /         |              "
    "        |      /          |              "
    " <pedal-wheel-boat>   <small-catamaran>  "
    "            \          /                 "
    "             \        /                  "
    "              \      /                   "
    "              <pedalo>                   "


    var Object=Class.def("Object",[],function(supr){return {
      whoami:function(){
        return ["object"].concat(
          _next(this,supr.log,arguments))}}})

    var Boat=Class.def("Boat",[Object],function(supr){return {
      whoami:function(){
        return ["boat"].concat(
          _next(this,supr.log,arguments))}}})

    var DayBoat=Class.def(
      "DayBoat",[Boat],function(supr){return {
        whoami:function(){
          return ["day-boat"].concat(
            _next(this,supr.log,arguments))}}})

    var WheelBoat=Class.def(
      "WheelBoat", [Boat],function(supr){return {
        whoami:function(){
          return ["wheel-boat"].concat(
            _next(this,supr.log,arguments))}}})

    var EngineLess=Class.def(
      "EngineLess", [DayBoat],function(supr){return {
        whoami:function(){
          return ["engine-less"].concat(
            _next(this,supr.log,arguments))}}})

    var PedalWheelBoat=Class.def(
      "PedalWheelBoat", [EngineLess,WheelBoat],function(supr){return {
        whoami:function(){
          return ["pedal-wheel-boat"].concat(
            _next(this,supr.log,arguments))}}})

    var SmallMultihull=Class.def(
      "SmallMultihull", [DayBoat],function(supr){return {
        whoami:function(){
          return ["small-multihull"].concat(
            _next(this,supr.log,arguments))}}})

    var SmallCatamaran=Class.def(
      "SmallCatamaran",[SmallMultihull],function(supr){return {
        whoami:function(){
          return ["small-catamaran"].concat(
            _next(this,supr.log,arguments))}}})

    var Pedalo=Class.def(
      "Pedalo",[PedalWheelBoat,SmallCatamaran],function(supr){return {
        whoami:function(){
          return ["pedalo"].concat(
            _next(this,supr.log,arguments))}}})

    debugger;
    var p0=Pedalo.new()
    console.log(p0.whoami())



  }
}



