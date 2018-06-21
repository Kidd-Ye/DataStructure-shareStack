# DataStructure-shareStack
A example of share stack.
<pre><code>

#define maxsize 100

class ShareStack
{
public:
    ShareStack(){
        top1 = -1;
        top2 = maxsize;
    }
    ~ShareStack(){}
    void Push(int i, int x);
    int Pop(int i);
    int GetTop(int i);
    bool Empty(int i);
private:
    int data[maxsize];
    int top1,top2;
};

void ShareStack::Push(int i, int x)
{
    if (top1 == top2-1) {
        cout<< "stack is full" <<endl;
        return;
    }
    if (i == 1) {
        data[++top1] = x;
    }
    if (i == 2) {
        data[--top2] = x;
    }
}

int ShareStack::Pop(int i){
    if (i == 1) {
        if (top1 == -1) {
            cout<< "stack1 is empty" <<endl;
        }else{
            return data[top1--];
        }
    }
    if (i == 2) {
        if (top2 == maxsize) {
            cout<< "stack2 is empty" <<endl;
        }else{
            return data[top2++];
        }
    }
    return 10000;
}

int ShareStack::GetTop(int i)
{
    if (i == 1) {
        if (top1 == -1) {
            cout<< "stack1 is empty" <<endl;
        }else{
            return data[top1];
        }
    }
    if (i == 2) {
        if (top1 == maxsize) {
            cout<< "stack2 is empty" <<endl;
        }else{
            return data[top2];
        }
    }
    return 10000;
}

bool ShareStack::Empty(int i)
{
    if (i == 1) {
        if (top1 == -1) {
            return true;
        }
        else return false;
    }
    if (i == 2) {
        if (top2 == maxsize) {
            return true;
        }
        else return false;
    }
    return 100000;
}

</code></pre>
