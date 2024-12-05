# Configurações adicionais do Cypress

---

### **Código**

```javascript
Cypress.on('uncaught:exception', (err, runnable) => {
    // Ignora os erros e impede falhas no teste
    return false;
  });
  
  import 'cypress-file-upload';
