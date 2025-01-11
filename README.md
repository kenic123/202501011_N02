# 202501011_N02
代码：

class Solution:
    def canConstruct(self, ransomNote: str, magazine: str) -> bool:
        # 使用字典来统计magazine中每个字符的数量
        mag_dict = {}
        for char in magazine:
            if char in mag_dict:
                mag_dict[char] += 1
            else:
                mag_dict[char] = 1

        # 遍历赎金信中的每个字符
        for char in ransomNote:
            # 如果字符不在magazine中或者magazine中该字符的数量已经为0，则返回False
            if char not in mag_dict or mag_dict[char] == 0:
                return False
            # 否则，将该字符的数量减1
            mag_dict[char] -= 1

        # 如果所有字符都被成功匹配，则返回True
        return True

# LeetCode 的测试代码
if __name__ == "__main__":
    solution = Solution()
    ransomNote = "aa"
    magazine = "aab"
    print(solution.canConstruct(ransomNote, magazine))  # 输出: True
### 截图
![alt text](image.png)