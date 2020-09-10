
 The memory error occurs when the allocation of memory associated to the pointer "result", 
 initially called in strip(), is not freed after it is done being used. 
 It first has to pass the results to the function that called it is_clean(). 
 From there it is associated to the pointer "cleaned" and then once it is used it can be freed.
 free(cleaned)
 There has to be a conditional to deal with non allocated cases such as if strip() exits when there is an empty string.  Since this bypasses the allocation then we need to bypass the freeing as that is an undefined action.

 Thus

 if (strcmp(cleaned, "") != 0) {
 	free(cleaned);
 }

 was my solution
