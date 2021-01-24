makeCacheMatrix <- function(x = matrix()) {

invrs <- NULL #stores the inversion

#sets a matric to object created by makeCacheMatrix

set <- function(y) {

x <<- y

invrs <<- NULL

}
get <- function() x

setinverse <- function(inverse) invrs <- inverse

getinverse <- function() invrs

#a list containing the function above

list(set = set, get = get,

setinverse = setinverse,

getinverse = getinverse)

}






cacheSolve <- function(x, ...) {

##Return a matrix that is inverse of 'x'

invrs <= x$getinverse()

if(!is.null(invrs)) {

message("getting cached data")

return(invrs)

}

mat <- x$get()

invrs <- solve(mat, ...) #solve it

x$setinverse(invrs) #store it

invrs

}

