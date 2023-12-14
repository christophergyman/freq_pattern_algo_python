
#Pseudo code implementation:

class Node:
    init (self, item, freq, parent):
        initialize all variables to itself
        self.item = item
        ...
        ...
        ...

def create_header_table(dataset, minimum_support):
    header_table = {}
    for transaction in dataset
        for item in transaction:
                header_table [item] = header table get (item, 0) + 1
    header_table = {k: v for k, v in header_table.items() if v >= min_support}

def update tree (item, node, header_table):
    if item in node.child:
        node.child[item].frequency +=1
    else
        new node = node(item, 1, node)
        node.child[item] = new node

        if header_table[item][1] is none then
            header_table[item][1] is new node
        else:
            update_list(header_table[item][1], new node)

    return node.children[item]

def update_list(head, node):
    while head next is not NULL:
        head is head.next
    head.next is node

def fp_growth(dataset, min_support):
    header table is create_header_table (dataset, min_support)
    if length of header_table is 0:
        return nothing

    for item in header_table
    header_table at item is [header_tablep[item], None]

    root = node('Null', 1, None)
    for transcation in the dataset
        sorted_items = sorted (transactions, key: header_table.get(k, 0), reverseTrue)
        current node is root node
        for item in sorted items:
            current node is update tree (item, current node, header_table)

    frequent patterns array = []
    for item in header_table:
        base_pattern is empty array
        conditionalJ_tree is empty array
        node = header_table[item][1]
            while node is not empty:
                conditional_tree.append(node)
                node is node.parent
            for ct_node in the conditional tree:
                base pattern.append (ct_node.item)

            if length of base pattern > 1:
                append to freq patterns array
    return freq patterns

