## 开发者手册
__**目录**__
- [整体构架](#整体构架)
- [Reporter输入输出产生](#reprorter)

### 整体构架


### Reporter

#### Reporter概述

 <img src='https://g.gravizo.com/svg?
@startuml;

Title "Reporter类图"
interface Listener；
abstract class SearchListener{
+         void searchStarted(Search *search)
+         void searchFinished(Search *searcher)
+         void stateAdvanced(Search *searcher)
+         void stateRemoved(Search *search, ExecutionState *state)
}；
abstract class VMListener{
   + void executeInstruction(VM *vm)
+ void instructionExecuted(VM *vm)
        + void objectCreated(VM *vm)
        + void objectDetroyed(VM *vm)
        + void methodEntered(VM *vm, Function *f)
        + void methodExited(VM *vm, Function *f)

}；
class Reporter{
- unsigned long long totalPaths
}；

Listener <|..  SearchListener；
Listener <|..  VMListener；
SearchListener  <|-- Reporter；

@enduml
'>
    

 
## 第二章

请输入第二章内容