# Application-level-Infix-to-Postfix-program-10

# Infix to Postfix Conversion - Calculator Application

def infix_to_postfix(exp):
    stack = []
    postfix = ""
    priority = {'+':1, '-':1, '*':2, '/':2}

    for ch in exp:
        if ch.isalnum():
            postfix += ch
        else:
            while stack and priority.get(stack[-1],0) >= priority[ch]:
                postfix += stack.pop()
            stack.append(ch)

    while stack:
        postfix += stack.pop()

    return postfix


# Application Example
expression = "A+B*C"

print("Infix Expression:", expression)
print("Postfix Expression:", infix_to_postfix(expression))



Infix Expression: A+B*C
Postfix Expression: ABC*+
