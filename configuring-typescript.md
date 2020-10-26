
## Configuring TypeScript Compilation

* Sử dụng file ```tsconfig.json``` để config cho tsc.
* Sử dụng câu lệnh sau để khởi tạo ```tsconfig.json``` basic file 
```base
tsc -init
```
* File config sẽ có dạng 
```
{
  "compilerOptions": {
    "target": "es5",                       
    "module": "commonjs",        
    "strict": true,                           
    "esModuleInterop": true,                
    "skipLibCheck": true,                    
    "forceConsistentCasingInFileNames": true  
  }
}

```
### Trong đó: 
* target(es5): Xác định rõ Javascript target version, khi typescript compile thành javacscript sẽ được compile thành version đó 
* module(commonjs): Xác định module loader system sẽ được sử dụng 
* strict(true): Enable tất cả các strict type-checking options

