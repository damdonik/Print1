section .data
    msg db "Hello, World!", 0

section .text
    global _start

_start:
    mov rax, 1         ; syscall: write
    mov rdi, 1         ; file descriptor: stdout
    mov rsi, msg       ; message to print
    mov rdx, 13        ; message length
    syscall

    mov rax, 60        ; syscall: exit
    xor rdi, rdi       ; status: 0
    syscall
