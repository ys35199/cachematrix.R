
## Put comments here that give an overall description of what your
## functions do

## Write a short comment describing this function

makeCacheMatrix <- function(x = matrix()) {
##set the x as a argument which is a type of matrix
##set inv as a placeholder for future values
             inv<-NULL
##set function for vector y 
             set<-function(y)
##assign the value of y to x in the parent environment
             x<<-y
##clear previous values of inv 
             inv<-NULL
##get the value x in the parent environment
             get<-funcion()x
##assign the inverse value to inv in the parent environment and set the invrse value
             setInverse<-function(inv) inv<<-inverse
##get the inverse value
             getInverse<-function()inv
##use list() to store them and each element is named 
##returns the 'special vector' containing all of the functions just defined 
             list(set=set,
                  get=get,
                  setinverse=setInverse,
                  getinverse=getInverse)
}


## Write a short comment describing this function

cacheSolve <- function(x, ...) {
## Return a matrix that is the inverse of 'x'
##R retrieve inverse value using getInverse() function
        inv <- x$getInverse()
##check whether there is a value in inv.If  the answer is TRUE, a cashed inverse returns to the parent environment.
        if (!is.null(inv)) {
                message("getting cached data")
                return(inv)
        }
##If the answer is FALSE, compute the inverse by calling solve()
        Dat <- x$get()
        inv <- solve(Dat, ...)
##set the inv value  and return it
        x$setInverse(inv)
        inv
}
