---
Error and exception handling
---
* In javascript, we use try/catch statements for error and  exception handling, the try statement allows people to define a block of code to be tested for errors and while it being execute. The catch statement. There are two types of try...catch clause, the first one is called the unconditional clause and the second one is called conditional clause:
* Examples of unconditional try...catch clause:

```
<script>
 Try { 
    addlert(“welcome guest!”); 
}
 Catch(err) { 
     document.getElementById(“demo”).innerHTML = err.message;
}
 </script>
```
* The second one is called conditional catch clauses:
 

```
<script>
  Try {
      XXXXX();
  }catch (e if e instanceof Typerror){ 
  }
  catch (e if e instanceof Rangerror){
  }
  catch(e if e instanceof EvalError){
  }
  catch(e) { 
  logMyErrors(e);
  }
 </script>
```
