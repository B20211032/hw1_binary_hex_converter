# hw1_binary_hex_converter
def decimal_to_binary(decimal_num):
    binary_num = ''
    for i in range(7, -1, -1):
        if decimal_num >= 2 ** i:
            binary_num += '1'
            decimal_num -= 2 ** i
        else:
            binary_num += '0'
    return binary_num

def decimal_to_hex(decimal_num):
    hex_num = ''
    quotient = decimal_num
    while quotient != 0:
        remainder = quotient % 16
        if remainder < 10:
            hex_num = str(remainder) + hex_num
        else:
            hex_num = chr(ord('A') + remainder - 10) + hex_num
        quotient //= 16
    return hex_num

def main():
    decimal_num = int(input("請輸入一個介於0到255之間的10進位數字："))
    if decimal_num < 0 or decimal_num > 255:
        print("輸入數字超出範圍，請重新輸入")
    else:
        binary_num = decimal_to_binary(decimal_num)
        hex_num = decimal_to_hex(decimal_num)
        print(f"二進位數字：{binary_num}")
        print(f"十六進位數字：{hex_num}")
    
if __name__ == '__main__':
    main()
