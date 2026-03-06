# Data-structure-partical-program-12
class Node:
    def __init__(self,x):
        self.x=x
        self.l=None
        self.r=None
        self.h=1

def h(n):
    return n.h if n else 0

def right(y):
    x=y.l
    y.l=x.r
    x.r=y
    return x

def insert(t,x):
    if not t: return Node(x)
    if x<t.x: t.l=insert(t.l,x)
    else: t.r=insert(t.r,x)
    return t

def delete(t,x):
    if not t: return t
    if x<t.x: t.l=delete(t.l,x)
    elif x>t.x: t.r=delete(t.r,x)
    else:
        if not t.l: return t.r
        if not t.r: return t.l
    return t

def inorder(t):
    if t:
        inorder(t.l)
        print t.x,
        inorder(t.r)

root=None
root=insert(root,30)
root=insert(root,20)
root=insert(root,40)

inorder(root)
root=delete(root,20)

print "\nAfter Delete:"
inorder(root)
