q1- qual é a moda ?

def conta_no_intervalo(nums, alvo, lo, hi):
    total = 0
    for i in range(lo, hi + 1):
        if nums[i] == alvo:
            total += 1
    return total


def moda_rec(nums, lo, hi):
    if lo == hi:
        return nums[lo]

    mid = (lo + hi) // 2
    esquerda = moda_rec(nums, lo, mid)
    direita = moda_rec(nums, mid + 1, hi)

    if esquerda == direita:
        return esquerda

    qtd_esquerda = conta_no_intervalo(nums, esquerda, lo, hi)
    qtd_direita = conta_no_intervalo(nums, direita, lo, hi)
    return esquerda if qtd_esquerda > qtd_direita else direita


def main():
    dados = input().split()
    nums = [int(x) for x in dados]
    print(moda_rec(nums, 0, len(nums) - 1))


if __name__ == '__main__':
    main()

---
q2 -escadas dinamicas

def escaladas(n):
    if n <= 2:
        return n

    anterior2, anterior1 = 1, 2
    for _ in range(3, n + 1):
        atual = anterior1 + anterior2
        anterior2, anterior1 = anterior1, atual
    return anterior1


def main():
    n = int(input())
    print(escaladas(n))


if __name__ == '__main__':
    main()
