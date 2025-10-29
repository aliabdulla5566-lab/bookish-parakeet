# bookish-parakeet
Life
// التحقق من صحة البطاقة
const validateCard = (cardNumber) => {
  // تنفيذ خوارزمية Luhn
  let sum = 0;
  let isEven = false;
  
  for (let i = cardNumber.length - 1; i >= 0; i--) {
    let digit = parseInt(cardNumber[i]);
    
    if (isEven) {
      digit *= 2;
      if (digit > 9) digit -= 9;
    }
    
    sum += digit;
    isEven = !isEven;
  }
  
  return sum % 10 === 0;
};

// تشفير البيانات
const encryptData = (data) => {
  // استخدام crypto library للتشفير
  return btoa(JSON.stringify(data)); // Base64 for demo
};