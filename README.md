# hw1_binary_hex_converter
def decimal_to_binary(decimal_num):
    bit_7, bit_6, bit_5, bit_4, bit_3, bit_2, bit_1, bit_0 = 128, 64, 32, 16, 8, 4, 2, 1
    binary_num = ''
    for bit in [bit_7, bit_6, bit_5, bit_4, bit_3, bit_2, bit_1, bit_0]:
        if decimal_num >= bit:
            binary_num += '1'
            decimal_num -= bit
        else:
            binary_num += '0'
    return binary_num


def decimal_to_hex(decimal_num, binary_num):
    hex_digits = '0123456789ABCDEF'
    hex_num = ''
    for i in range(0, len(binary_num), 4):
        hex_digit = 0
        for j in range(4):
            if i + j < len(binary_num):
                hex_digit = hex_digit * 2 + int(binary_num[i+j])
        hex_num += hex_digits[hex_digit]
    return hex_num


def main():
    decimal_num = int(input("請輸入一個介於0到255之間的10進位數字："))
    if decimal_num < 0 or decimal_num > 255:
        print("輸入數字超出範圍，請重新輸入")
    else:
        binary_num = decimal_to_binary(decimal_num)
        hex_num = decimal_to_hex(decimal_num, binary_num)
        print(f"二進位數字：{binary_num}")
        print(f"十六進位數字：{hex_num}")


if __name__ == '__main__':
    main()

