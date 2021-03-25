# gmssl-sm4-py

python3版本的sm4加解密算法

## 1. 用法

#### 1.1. 加密

```python
key = b'Fh9SNSU2ISwD9fWp'
crypt_sm4 = CryptSM4()

plain_text = '小马哥'
print('加密前， key: ', key, '明文: ', plain_text)
plain_text = plain_text.encode('utf-8')
crypt_sm4.set_key(key, SM4_ENCRYPT)
encrypt_value = crypt_sm4.crypt_ecb(plain_text)
encrypt_value = encrypt_value.hex()
print('加密后: ', encrypt_value, '类型: ', type(encrypt_value))
```

输出:

```
加密前， key:  b'Fh9SNSU2ISwD9fWp' 明文:  小马哥
加密后:  bd847d68f4b06ddc3c71dd80f6fb2346 类型:  <class 'str'>
```

#### 1.2. 解密

```python
key = b'Fh9SNSU2ISwD9fWp'
crypt_sm4 = CryptSM4()

cipher_text = 'bd847d68f4b06ddc3c71dd80f6fb2346'
print('解密前， key: ', key, '密文: ', cipher_text)
cipher_text = bytes.fromhex(cipher_text)
crypt_sm4.set_key(key, SM4_DECRYPT)
decrypt_value = crypt_sm4.crypt_ecb(cipher_text)
decrypt_value = str(crypt_sm4.crypt_ecb(cipher_text), encoding='UTF-8')
print('解密后: ', decrypt_value, '类型: ', type(decrypt_value))
```

输出：

```
解密前， key:  b'Fh9SNSU2ISwD9fWp' 密文:  bd847d68f4b06ddc3c71dd80f6fb2346
解密后:  小马哥 类型:  <class 'str'>
```

## 2. 测试

```python
$ python test.py

=====test sm4 start=====
加密前， key:  b'Fh9SNSU2ISwD9fWp' 明文:  小马哥
加密后:  bd847d68f4b06ddc3c71dd80f6fb2346 类型:  <class 'str'>
解密前， key:  b'Fh9SNSU2ISwD9fWp' 密文:  bd847d68f4b06ddc3c71dd80f6fb2346
解密后:  小马哥 类型:  <class 'str'>
=====test sm4 end=====
```
