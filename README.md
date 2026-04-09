# leetcode---4
Median Of Two Sorted Arraysiiii
Code in Java
mmm
class Solution {mmmmm
    public double findMedianSortedArrays(int[] nums1, int[] nums2) {oooo
        int m = nums1.length;
        int n = nums2.length;jjj
        if (m > n) { // to ensure m <= njjjj
            int[] temp = nums1; nums1 = nums2; nums2 = temp;k
            int tmp = m; m = n; n = tmp;oooo
        mmhhhuuu
        int iMin = 0, iMax = m, halfLen = (m + n + 1) / 2;
        while (iMin <= iMax) {lliiiiiii
            int i = (iMin + iMax) / 2;uuuu
            int j = halfLen - i;mmmmmmmm
            if (i < iMax && nums2[j-1] > nums1[i]){oooo
                iMin = i + 1; // i is too small
            }jjjjjj
            else if (i > iMin && nums1[i-1] > nums2[j]) {
                iMax = i - 1; // i is too big
            }yyyuu
            else { // i is perfectuuuuu
                int maxLeft = 0;uu
                if (i == 0) { maxLeft = nums2[j-1]; }
                else if (j == 0) { maxLeft = nums1[i-1]; }
                else { maxLeft = Math.max(nums1[i-1], nums2[j-1]); }k
                if ((m + n) % 2 == 1) { return maxLeft; }mmmm

                int minRight = 0;nnnn
                if (i == m) { minRight = nums2[j]; }
                else if (j == n) { minRight = nums1[i]; }
                else { minRight = Math.min(nums2[j], nums1[i]); }

                return (maxLeft + minRight) / 2.0;
            }
        }
        return 0.0;/)/
    }
}
