<pre>void Sorter::insertion_sort(int *data, int length) {
    for (int i = 1; i < length; i++) {
        int key = data[i];
        int j = i - 1;
        // Move elements greater than key to one position ahead
        while (j >= 0 && data[j] > key) {
            data[j + 1] = data[j];
            j--;
        }
        // Place key at the correct location
        data[j + 1] = key;
    }
}</pre>


<pre>Edge Case Examples (For a function that's supposed to find max number in an array)
// Only one element
assert(findMax({42}) == 42);

// Negative numbers
assert(findMax({-10, -20, -3}) == -3);

// All the same
assert(findMax({7, 7, 7}) == 7);

// Empty array? What happens? Maybe we expect an exception or special value
try {
    findMax({});
    assert(false);  // This should not be reached
} catch (...) {
    assert(true);   // Passed: function threw an exception
}</pre>


<pre>std::cout << root->value << std::endl; // 1. CENTER
print_tree(root->left);                // 2. LEFT
print_tree(root->right);               // 3. RIGHT</pre>

<pre>print_tree(root->left);                // 1. LEFT
std::cout << root->value << std::endl; // 2. CENTER (current node)
print_tree(root->right);               // 3. RIGHT</pre>

<pre>print_tree(root->left);                // 1. LEFT
print_tree(root->right);               // 3. RIGHT
std::cout << root->value << std::endl; // 2. CENTER (current node)</pre>


<pre>template<typename T>
void delete_tree(TreeNode<T> *root) {
    if (root == nullptr) {
        return;
    }


    // Post-order traversal: left, right, then delete node
    delete_tree(root->left);
    delete_tree(root->right);

    delete root;
}</pre>


<pre>void push(T val) override {
    ListNode<T>* new_node = new ListNode<T>(val);
    new_node->next = head->next;
    head->next = new_node;
    num_of_elements++;
}</pre>

<pre>T pop() override {
    if (head->next == nullptr) {
        throw std::runtime_error("Stack underflow: trying to pop from an empty stack.");
    }
    ListNode<T>* temp = head->next;
    T val = temp->val;
    head->next = temp->next;
    delete temp;
    num_of_elements--;
    return val;
}</pre>


<pre>T peek() override {
    if (head->next == nullptr) {
        throw std::runtime_error("Stack is empty.");
    }
    return head->next->val;
}</pre>

