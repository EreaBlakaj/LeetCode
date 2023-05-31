#include <iostream>
#include<vector>
#include<stack>
#include <queue>
#include <unordered_map>

using namespace std;

//Definition for a binary tree node.
struct TreeNode {
    int val;
    TreeNode* left;
    TreeNode* right;
    TreeNode() : val(0), left(nullptr), right(nullptr) {}
    TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
    TreeNode(int x, TreeNode* left, TreeNode* right) : val(x), left(left), right(right) {}
};

//Definition for singly - linked list.
struct ListNode {
    int val;
    ListNode* next;
    ListNode() : val(0), next(nullptr) {}
    ListNode(int x) : val(x), next(nullptr) {}
    ListNode(int x, ListNode* next) : val(x), next(next) {}

};

struct problem {
	//Detyra me Stacks
	//Detyra 1: 225. Implement Stack using Queues
    class MyStack {
    private:
        queue<int> q1;
        queue<int>q2;
        int topElement;
    public:
        MyStack() {
        }
        void push(int x) {
            q1.push(x);
            topElement = x;
        }
        int pop() {
            while (q1.size() > 1) {
                topElement = q1.front();
                q2.push(topElement);
                q1.pop();
            }
            int removedElement = q1.front();
            q1.pop();
            swap(q1, q2);
            return removedElement;
        }
        int top() {
            return topElement;
        }
        bool empty() {
            return q1.empty();
        }
    };

    //Detyra 2: 232. Implement Queue using Stacks
    class MyQueue {
    private:
        stack<int> inS;
        stack<int> outS;
    public:
        MyQueue() {

        }
        void push(int x) {
            inS.push(x);
        }
        int pop() {
            if (outS.empty()) {
                while (!inS.empty()) {
                    outS.push(inS.top());
                    inS.pop();
                }
            }
            int firstElement = outS.top();
            outS.pop();
            return firstElement;
        }
        int peek() {
            if (outS.empty()) {
                while (!inS.empty()) {
                    outS.push(inS.top());
                    inS.pop();
                }
            }
            return outS.top();
        }
        bool empty() {
            return inS.empty() && outS.empty();
        }
    };

    //Detyra 3: 1381. Design a Stack With Increment Operation
    class CustomStack {
    private:
        stack<int> steku;
        int maxSize;
    public:
        CustomStack(int maxSize) {
            this->maxSize = maxSize;
        }
        void push(int x) {
            if (steku.size() < maxSize) {
                steku.push(x);
            }
        }
        int pop() {
            if (steku.empty())
                return -1;

            int topElement = steku.top();
            steku.pop();
            return topElement;
        }
        void increment(int k, int val) {
            stack<int> stekuDyte;

            while (steku.size() > k) {
                stekuDyte.push(steku.top());
                steku.pop();
            }
            while (steku.size()) {
                steku.top() += val;
                stekuDyte.push(steku.top());
                steku.pop();
            }
            while (!stekuDyte.empty()) {
                steku.push(stekuDyte.top());
                stekuDyte.pop();
            }
        }
    };

    //Detyra me Queue
    //Detyra 4: 933. Number of Recent Calls
    class RecentCounter {
    private:
        queue<int> q;
    public:
        RecentCounter() {

        }
        int ping(int t) {
            q.push(t);
            while (q.front() < t - 3000) {
                q.pop();
            }
            return q.size();
        }
    };

    //Detyra 5: 1700. Number of Students Unable to Eat Lunch
    class Solution5 {
    public:
        int countStudents(vector<int>& students, vector<int>& sandwiches) {
            int n = students.size();
            queue<int> studentQueue;
            queue<int> sandwichQueue;
            for (int i = 0; i < n; i++) {
                studentQueue.push(students[i]);
                sandwichQueue.push(sandwiches[i]);
            }
            int paBuk = 0;
            while (!studentQueue.empty()) {
                if (studentQueue.front() == sandwichQueue.front()) {
                    studentQueue.pop();
                    sandwichQueue.pop();
                    paBuk = 0;
                }
                else {
                    studentQueue.push(studentQueue.front());
                    studentQueue.pop();
                    paBuk++;
                }
                if (paBuk == n) {
                    break;
                }
            }
            return studentQueue.size();
        }
    };

    //Detyra 6: 2073. Time Needed to Buy Tickets
    class Solution6 {
    public:
        int timeRequiredToBuy(vector<int>& tickets, int k) {
            int count = 0;
            int i = 0;
            int n = tickets.size();
            while (tickets[k] != 0) {
                if (tickets[i] != 0) {
                    tickets[i]--;
                    count++;
                }
                i++;
                if (i == n) {
                    i = 0;
                }
            }
            return count;
        }
    };

    //Detyra me Sorting
    //Detyra 7: 268. Missing Number
    class Solution7 {
    public:
        int missingNumber(vector<int>& nums) {
            int n = nums.size() + 1;
            int shuma1 = (n * (n - 1)) / 2;
            for (int i = 0; i < nums.size(); i++) {
                shuma1 -= nums[i];
            }
            return shuma1;
        }
    };

    //Detyra 8: 561. Array Partition
    class Solution8 {
    public:
        int arrayPairSum(vector<int>& nums) {
            sort(nums.begin(), nums.end());
            int sum = 0;
            for (int i = 0; i < nums.size(); i += 2) {
                sum += nums[i];
            }
            return sum;
        }
    };

    //Detyra 9: 88. Merge Sorted Array
    class Solution9 {
    public:
        void merge(vector<int>& nums1, int m, vector<int>& nums2, int n) {
            for (int i = 0; i < n; i++) {
                nums1[m + i] = nums2[i];
            }
            sort(nums1.begin(), nums1.end());
        }
    };

    //Detyra Greedy
    //Detyra 10: 976. Largest Perimeter Triangle
    class Solution10 {
    public:
        int largestPerimeter(vector<int>& nums) {
            int perimetri = 0;
            sort(nums.begin(), nums.end());
            for (int i = nums.size() - 1; i >= 2; i--) {
                if (nums[i - 1] + nums[i - 2] > nums[i]) {
                    perimetri = nums[i] + nums[i - 1] + nums[i - 2];
                    break;
                }
            }
            return perimetri;
        }
    };

    //Detyra 11: 409. Longest Palindromeclass Solution 
    class Solution11{
    public:
    int longestPalindrome(string s) {
        int tek = 0;
        unordered_map<char, int> map;
        for (int i = 0; i < s.size(); i++) {
            char ch = s[i];
            map[ch]++;
            if (map[ch] % 2 == 1) {
                tek++;
            }
            else {
                tek--;
            }
        }
        if (tek > 1) {
            return s.length() - tek + 1;
        }
        return s.length();
    }
};

    //Detya 12: 860. Lemonade Change
    class Solution12 {
    public:
        bool lemonadeChange(vector<int>& bills) {
            int pese = 0, dhjete = 0;
            for (int i = 0; i < bills.size(); i++) {
                int bill = bills[i];
                if (bill == 5) {
                    pese++;
                }
                else if (bill == 10) {
                    if (pese == 0) {
                        return false;
                    }
                    pese--;
                    dhjete++;
                }
                else {
                    if (dhjete > 0 && pese > 0) {
                        dhjete--;
                        pese--;
                    }
                    else if (pese >= 3) {
                        pese -= 3;
                    }
                    else {
                        return false;
                    }
                }
            }
            return true;
        }
    };

    //Detyra me Binary Search
    //Detyra 13: 704. Binary Search
    class Solution13 {
    public:
        int search(vector<int>& nums, int target) {
            int min = 0, max = nums.size() - 1;
            int mid = (min + max) / 2;
            while (min <= max) {
                if (nums[mid] == target) {
                    return mid;
                }
                if (target > nums[mid]) {
                    min = mid + 1;
                }
                else if (target < nums[mid]) {
                    max = mid - 1;
                }
                mid = (min + max) / 2;
            }
            return -1;
        }
    };

    //Detyra 14: 350. Intersection of Two Arrays II
    class Solution14 {
    public:
        vector<int> intersect(vector<int>& nums1, vector<int>& nums2) {
            sort(nums1.begin(), nums1.end());
            sort(nums2.begin(), nums2.end());
            vector<int> zgjidhja;
            int n = nums1.size(), m = nums2.size();
            int i = 0, j = 0;
            while (i < n && j < m) {
                if (nums1[i] == nums2[j]) {
                    zgjidhja.push_back(nums1[i]);
                    i++;
                    j++;
                }
                else if (nums1[i] < nums2[j]) {
                    i++;
                }
                else {
                    j++;
                }
            }
            return zgjidhja;
        }
    };

    //Detyra 15: 35. Search Insert Position
    class Solution15 {
    public:
        int searchInsert(vector<int>& nums, int target) {
            int min = 0, max = nums.size();
            int mes = (min + max) / 2;
            if (target > nums[max - 1]) {
                return max;
            }
            while (min <= max) {
                mes = (min + max) / 2;
                if (nums[mes] == target) {
                    return mes;
                }
                if (target > nums[mes]) {
                    min = mes + 1;
                }
                else if (target < nums[mes]) {
                    max = mes - 1;
                }
            }
            return min;
        }
    };

    //Detyra me Tree
    //Detyra 16: 94. Binary Tree Inorder Traversal
    class Solution16 {
    public:
        vector<int> inorderTraversal(TreeNode* root) {
            vector<int> zgjidhja;
            stack<TreeNode*> stackNodes;
            TreeNode* rn = root;
            while (rn != nullptr || !stackNodes.empty()) {

                while (rn != nullptr) {
                    stackNodes.push(rn);
                    rn = rn->left;
                }
                rn = stackNodes.top();
                stackNodes.pop();
                zgjidhja.push_back(rn->val);
                rn = rn->right;
            }
            return zgjidhja;
        }
    };

    //Detyra 17: 104. Maximum Depth of Binary Tree
    class Solution17 {
    public:
        int maxDepth(TreeNode* root) {
            if (root == nullptr) {
                return 0;
            }

            int lDepth = maxDepth(root->left);
            int rDepth = maxDepth(root->right);

            return max(lDepth, rDepth) + 1;
        }
    };

    //Detyra 18: 100. Same Tree
    class Solution18 {
    public:
        bool isSameTree(TreeNode* p, TreeNode* q) {
            if (p == nullptr && q == nullptr) {
                return true;
            }
            else if (p == nullptr || q == nullptr) {
                return false;
            }
            if (p->val != q->val) {
                return false;
            }
            return (isSameTree(p->left, q->left) && isSameTree(p->right, q->right));
        }
    };

    //Detyra me LinkedLists
    //Detyera 19: 206. Reverse Linked List
    class Solution19 {
    public:
        ListNode* reverseList(ListNode* head) {
            ListNode* para = nullptr;
            ListNode* tash = head;
            while (tash != nullptr) {
                ListNode* pas = tash->next;
                tash->next = para;
                para = tash;
                tash = pas;
            }
            return para;
        }
    };

    //Detyra 20: 21. Merge Two Sorted Lists
    class Solution20 {
    public:
        ListNode* mergeTwoLists(ListNode* list1, ListNode* list2) {
            if (list1 == nullptr) {
                return list2;
            }
            if (list2 == nullptr) {
                return list1;
            }
            if (list1->val <= list2->val) {
                list1->next = mergeTwoLists(list1->next, list2);
                return list1;
            }
            else {
                list2->next = mergeTwoLists(list1, list2->next);
                return list2;
            }
        }
    };
};



int main() {
    problem::MyStack myStack;
    myStack.push(1);
    myStack.push(2);
    cout << myStack.top() << endl;
    cout << myStack.pop() << endl;
    cout << myStack.empty() << endl;


    problem::CustomStack stack(3);
    stack.push(1);
    stack.push(2);
    cout << stack.pop() << endl;
    stack.push(2);
    stack.push(3);
    stack.push(4);
    stack.increment(5, 100);
    stack.increment(2, 100);
    cout << stack.pop() << endl;
    cout << stack.pop() << endl;
    cout << stack.pop() << endl;
    cout << stack.pop() << endl;

    problem::MyQueue queue;
    queue.push(1);
    queue.push(2);
    cout << queue.peek() << endl;
    cout << queue.pop() << endl;
    cout << queue.empty() << endl;

    problem::RecentCounter counter;
    cout << counter.ping(1) << endl;
    cout << counter.ping(100) << endl;
    cout << counter.ping(3001) << endl;
    cout << counter.ping(3002) << endl;

    vector<int> students{ 1, 1, 0, 0 }, sandwiches{ 0,1,0,1 };
    problem::Solution5 sol5;
    cout << sol5.countStudents(students, sandwiches) << endl;

    vector<int> tickets{ 2,3,2 };
    int k = 2;
    problem::Solution6 sol6;
    cout << sol6.timeRequiredToBuy(tickets, k) << endl;

    vector<int> nums{ 3,0,1 };
    problem::Solution7 sol7;
    cout << sol7.missingNumber(nums) << endl;

    vector<int> nums1{ 1,4,3,2 };
    problem::Solution8 sol8;
    cout << sol8.arrayPairSum(nums1) << endl;

    vector<int> nums2{ 1, 2, 3, 0, 0, 0 }, nums3{ 2,5,6 };
    int m = 3, n = 3;
    problem::Solution9 sol9;
    sol9.merge(nums2, m, nums3, n);
    for (int i = 0; i < nums2.size(); i++) {
        cout << nums2[i]<<" ";
    }
    cout << endl;

    vector<int>nums4{ 2,1,2 };
    problem::Solution10 sol10;
    cout << sol10.largestPerimeter(nums4) << endl;

    string s = "abccccdd";
    problem::Solution11 sol11;
    cout << sol11.longestPalindrome(s) << endl;

    vector<int> nums5{5,5,5,10,20};
    problem::Solution12 sol12;
    cout << sol12.lemonadeChange(nums5) << endl;

    vector<int> nums6{ - 1,0,3,5,9,12 };
    int target = 9;
    problem::Solution13 sol13;
    cout << sol13.search(nums6, target) << endl;

    vector<int> nums7{ 1,2,2,1 }, nums8{ 2,2 };
    problem::Solution14 sol14;
    vector<int> zgjidhja = sol14.intersect(nums7, nums8);
    for (int i = 0; i < zgjidhja.size(); i++) {
        cout << zgjidhja[i]<<" ";
    }
    cout<< endl;

    vector<int> nums9{ 1,3,5,6 };
    int target2 = 5;
    problem::Solution15 sol15;
    cout << sol15.searchInsert(nums9, target2) << endl;

}


