## Assembly
section .data
    nama db 'Halo, Saya Bagas Prabowo', 0xa
    panjang equ $ - nama

section .text
    global _start

_start:
    mov rax, 1             ; sys_write
    mov rdi, 1             ; stdout
    mov rsi, nama          ; alamat string
    mov rdx, panjang       ; panjang string
    syscall

    mov rax, 60            ; sys_exit
    xor rdi, rdi
    syscall
