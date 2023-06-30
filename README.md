# sothienthan
import random

def find_amicable_pair():
    # Khởi tạo danh sách để lưu các cặp số thân thiết
    amicable_pairs = []

    # Duyệt qua tất cả các số trong khoảng từ 1 đến 1000
    for num1 in range(1, 1000):
        sum1 = sum_of_divisors(num1)
        if sum1 != num1:  # Kiểm tra điều kiện 1: Số này không phải là số hoàn hảo
            num2 = sum1
            sum2 = sum_of_divisors(num2)
            if sum2 == num1:  # Kiểm tra điều kiện 2: Số thứ hai là tổng các ước số của số đầu tiên và ngược lại
                pair = (num1, num2)
                amicable_pairs.append(pair)

    # Chọn ngẫu nhiên một cặp số thân thiết từ danh sách các cặp số thân thiết
    random_pair = random.choice(amicable_pairs)
    return random_pair

def sum_of_divisors(n):
    # Tính tổng các ước số của số n
    divisors_sum = 0
    for i in range(1, n):
        if n % i == 0:
            divisors_sum += i
    return divisors_sum

# Gọi hàm để tìm và in ra một cặp số thân thiết ngẫu nhiên
pair = find_amicable_pair()
print("Cặp số thân thiết ngẫu nhiên:", pair)
