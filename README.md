# tab-11
import math


def doira_maydoni(radius: float = 1.0) -> float:
    if radius < 0:
        raise ValueError("Radius manfiy bo'lishi mumkin emas!")
    return math.pi * (radius ** 2)


def doira_perimetri(radius: float = 1.0) -> float:
    if radius < 0:
        raise ValueError("Radius manfiy bo'lishi mumkin emas!")
    return 2 * math.pi * radius


def tortburchak_maydoni(uzunlik: float = 4.0, eni: float = 2.0) -> float:
    if uzunlik < 0 or eni < 0:
        raise ValueError("O'lchamlar manfiy bo'lishi mumkin emas!")
    return uzunlik * eni


def tortburchak_perimetri(uzunlik: float = 4.0, eni: float = 2.0) -> float:
    if uzunlik < 0 or eni < 0:
        raise ValueError("O'lchamlar manfiy bo'lishi mumkin emas!")
    return 2 * (uzunlik + eni)


def uchburchak_maydoni(asos: float = 3.0, balandlik: float = 4.0) -> float:
    if asos < 0 or balandlik < 0:
        raise ValueError("O'lchamlar manfiy bo'lishi mumkin emas!")
    return 0.5 * asos * balandlik


def uchburchak_perimetri(a: float = 3.0, b: float = 4.0, c: float = 5.0) -> float:
    if a < 0 or b < 0 or c < 0:
        raise ValueError("Tomonlar manfiy bo'lishi mumkin emas!")
    return a + b + c


def asosiy_menyu():
    print("--- Geometrik hisob-kitob menyusi ---")
    print("1. Doira")
    print("2. To'rtburchak")
    print("3. Uchburchak")

    tanlov = input("Raqamni tanlang (1/2/3): ")

    try:
        if tanlov == '1':
            r = float(input("Radiusni kiriting (standart 1 uchun Enter bosing): ") or 1)
            area = doira_maydoni(r)
            perimeter = doira_perimetri(r)
            print(f"\nNatija (Doira): Maydoni = {area:.4f}, Perimetri = {perimeter:.4f}")

        elif tanlov == '2':
            uzunlik = float(input("Uzunlikni kiriting (standart 4 uchun Enter bosing): ") or 4)
            eni = float(input("Enini kiriting (standart 2 uchun Enter bosing): ") or 2)
            area = tortburchak_maydoni(uzunlik, eni)
            perimeter = tortburchak_perimetri(uzunlik, eni)
            print(f"\nNatija (To'rtburchak): Maydoni = {area:.2f}, Perimetri = {perimeter:.2f}")

        elif tanlov == '3':
            asos = float(input("Asosini kiriting (standart 3 uchun Enter bosing): ") or 3)
            balandlik = float(input("Balandligini kiriting (standart 4 uchun Enter bosing): ") or 4)
            a = float(input("1-tomonni kiriting (standart 3 uchun Enter bosing): ") or 3)
            b = float(input("2-tomonni kiriting (standart 4 uchun Enter bosing): ") or 4)
            c = float(input("3-tomonni kiriting (standart 5 uchun Enter bosing): ") or 5)

            area = uchburchak_maydoni(asos, balandlik)
            perimeter = uchburchak_perimetri(a, b, c)
            print(f"\nNatija (Uchburchak): Maydoni = {area:.2f}, Perimetri = {perimeter:.2f}")
        else:
            print("Noto'g'ri tanlov! Iltimos, 1, 2 yoki 3 raqamini tanlang.")
    except ValueError as e:
        print(f"\nXatolik: {e}")


if __name__ == "__main__":
    asosiy_menyu()
