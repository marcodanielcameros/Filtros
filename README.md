# Filtros
## Filtros en Java Backend


Index.jsp |  Filtro.jsp
--------- | ----------
Direccionado si no ocurre nada especial | Si el link esta registrado se mandara el html de Filtro a index

**Codigo importante donde ocurre la magia**
*Funcion del archivo filtrolp.java*

```Java
    public void doFilter(ServletRequest request, ServletResponse response,
            FilterChain chain)
            throws IOException, ServletException {
        
        System.out.println(" "+request.getParameter("Mensajillo"));
        
        System.out.println("La ip del batillo loco es "+request.getRemoteAddr());
        if(request.getRemoteAddr().equals("192.168.10.23")){
            System.out.println("El va loco");
            RequestDispatcher rq = request.getRequestDispatcher("/filtro.jsp");
            rq.forward(request, response);
        }
        
        chain.doFilter(request, response);   
    }
```
