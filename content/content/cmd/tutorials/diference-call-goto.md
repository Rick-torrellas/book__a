---
title: "Diferencia entre call y goto"
description: ""
---

# Diferencia entre call y goto

* goto - goes to the label.
* call - goes to the label and then returns to the caller when the code is complete.

call also allows parameters to be passed. As far as the subroutine that is the target of the call, its %1... are the parameters provided by the call, not as provided as command-line parameters to the batch procedure.  

You can call an external batch or executable, and at the end of that called routine, execution will resume with the instruction after the call. goto will simply execute the target, and completely forget where it was in the original batch.  
