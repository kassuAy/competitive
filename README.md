# competitive
class Solution:
    def checkArithmeticSubarrays(self, nums: List[int], l: List[int], r: List[int]) -> List[bool]:
        L=len(nums)
        def good(left,right):
            k=list(sorted(nums[left:right+1]))
            if len(k)==1:
                return True
            alpha=k[1]-k[0]
            for x,y in zip(k,k[1:]):
                if y-x !=alpha:
                    return  False
            return True

        result=[]
        for left,right in zip(l,r):
            result+=[good(left,right)]
        return result
