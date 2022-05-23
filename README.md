# Max-sum-contigous-subarray
Max sum contigous subarray in Python
arr=[-2,-3,4, -1, -2, 1, 5, -3]  # given array
n=len(arr) # store len of arr in a variable for simplicity
asum=arr[0]    #1st variable consider it as 1st elem of given array
amax=arr[0]    #2nd variable consider it as 1st elem of given array
endi=0         #3rd variable 
si=0          # 4th variable
for i in range (1,n):   #traverse in array
	asum=max(arr[i],arr[i]+asum)   # update 1st variable with max value of array
	if asum>amax:    # if sum> max value
		amax=asum      # update max value b sum.
		endi=i         # update endi variable with index value of max elem among arr
si=endi            #update Si with index value of max elem among arr.
while(si>=0):      # Traverse in left direction for  find start Index of subarray
	amax-=arr[si]
	if amax==0:
		break
	si-=1
for i in range(si,endi+1):
	print(arr[i],end=" ")
