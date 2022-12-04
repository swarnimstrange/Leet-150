<h3> Problem </h3>
Given two integer arrays nums1 and nums2, return an array of their intersection. Each element in the result must appear as many times as it shows in both arrays and you may return the result in any order.

<pre>
    Input: nums1 = [1,2,2,1], nums2 = [2,2]
    Output: [2,2]
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: Sort both arrays and take two pointers i and j and an empty array.
Step 2: Loop until i is smaller than len(list1) and j is smaller than len(list2).
Step 3: if list1[i] > list2[j] it means j needs to be greater to be equal to list[i] so we increment j by 1
Step 4: opposite of above case in i. so we increment i by 1
Step 5: if both elements of lists becomes equal we append into empty array and increment both i and j by 1.
Step 6: If it comes out of loop return the array.
</pre>

<h3> Code in Python </h3>

<pre><code>  def intersect(self, nums1: List[int], nums2: List[int]) -> List[int]:
        res = []
        nums1.sort()
        nums2.sort()
        i = 0
        j = 0
        while i < len(nums1) and j < len(nums2):
            if nums1[i] > nums2[j]:
                j+=1
            elif nums1[i] < nums2[j]:
                i+=1
            else:
                res.append(nums1[i])
                i+=1
                j+=1
        return res </code> </pre>
