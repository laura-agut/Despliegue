---
title: Despliegue de aplicaciones web
---
![](img/DespliegueAplicacionesWeb2.png)

## 📑 Índice

<p style="margin:.5rem 0 1rem; color:#374151;">
Apuntes y prácticas del módulo <b>Despliegue de aplicaciones web</b> de <u>2º de DAW</u>
</p>

<ul style="list-style:none; padding:0; margin:0; display:grid; grid-template-columns:1fr; gap:.3rem; max-width:700px;">
  <li style="background:#f8fafc; border:1px solid #e5e7eb; border-radius:6px;">
    <a href="Ud0 Introduccion/Ud0_1Introalmodulo/" style="display:block; padding:.45rem .65rem; text-decoration:none;">0 – Introducción</a>
  </li>
  <li style="background:#f8fafc; border:1px solid #e5e7eb; border-radius:6px;">
    <a href="Ud1 ControlVersiones/T01_index_git/" style="display:block; padding:.45rem .65rem; text-decoration:none;">1 – Control de versiones</a>
  </li>
  <li style="background:#f8fafc; border:1px solid #e5e7eb; border-radius:6px;">
    <a href="Ud2 Contenedores/" style="display:block; padding:.45rem .65rem; text-decoration:none;">2 – Contenedores</a>
  </li>
  <li style="background:#f8fafc; border:1px solid #e5e7eb; border-radius:6px;">
    <a href="Ud3 ArquitecturaWeb/" style="display:block; padding:.45rem .65rem; text-decoration:none;">3 – Arquitectura web – Servidores web</a>
  </li>
  <li style="background:#f8fafc; border:1px solid #e5e7eb; border-radius:6px;">
    <a href="Ud6_ServidoresAplicaciones.md" style="display:block; padding:.45rem .65rem; text-decoration:none;">4 – Servidores de aplicaciones</a>
  </li>
  <li style="background:#f8fafc; border:1px solid #e5e7eb; border-radius:6px;">
    <a href="Ud7_CICD.md" style="display:block; padding:.45rem .65rem; text-decoration:none;">5 – CI/CD</a>
  </li>
  <li style="background:#f8fafc; border:1px solid #e5e7eb; border-radius:6px;">
    <a href="Ud4_ServiciosRed1.md" style="display:block; padding:.45rem .65rem; text-decoration:none;">6 – Servicios de red (DNS y LDAP)</a>
  </li>
  <li style="background:#f8fafc; border:1px solid #e5e7eb; border-radius:6px;">
    <a href="Ud5_ServiciosRed2.md" style="display:block; padding:.45rem .65rem; text-decoration:none;">7 – Servicios de red (FTP)</a>
  </li>
</ul>

<style>
ul[style] a:hover{
  background:#eef2ff;
}
</style>


<style>
/* Hover sutil y responsivo */
ul[style] a:hover{ background:#eef2ff; }
@media (max-width: 800px){
  ul[style]{ grid-template-columns:1fr; }
}
</style>



## 📊 Tabla de versiones

<div style="overflow-x:auto; margin-top:1rem;">

<table style="width:100%; border-collapse:collapse; text-align:left;">
  <thead style="background:#f3f4f6;">
    <tr>
      <th style="padding:0.75rem; border-bottom:2px solid #e5e7eb;">Versión</th>
      <th style="padding:0.75rem; border-bottom:2px solid #e5e7eb;">Autor</th>
      <th style="padding:0.75rem; border-bottom:2px solid #e5e7eb;">Comentarios</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="padding:0.75rem; border-bottom:1px solid #e5e7eb;">0.0</td>
      <td style="padding:0.75rem; border-bottom:1px solid #e5e7eb;">
        <a href="mailto:r.riesco@edu.gva.es">Raúl Riesco Montes</a>
      </td>
      <td style="padding:0.75rem; border-bottom:1px solid #e5e7eb;">
        Versión original de estos apuntes (IES Severo Ochoa de Elche).
      </td>
    </tr>
    <tr>
      <td style="padding:0.75rem; border-bottom:1px solid #e5e7eb;">Curso 23/24</td>
      <td style="padding:0.75rem; border-bottom:1px solid #e5e7eb;">
        <a href="https://about.me/jmunozj" target="_blank">José Muñoz Jimeno</a> y Noelia Beltrán Mañas
      </td>
      <td style="padding:0.75rem; border-bottom:1px solid #e5e7eb;">
        Adaptación de los materiales a nueva normativa y necesidades del IES El Caminàs.
      </td>
    </tr>
    <tr>
      <td style="padding:0.75rem; border-bottom:1px solid #e5e7eb;">Curso 24/25</td>
      <td style="padding:0.75rem; border-bottom:1px solid #e5e7eb;">
        <a href="https://about.me/jmunozj" target="_blank">José Muñoz Jimeno</a>
      </td>
      <td style="padding:0.75rem; border-bottom:1px solid #e5e7eb;">
        Modificación de los materiales para el nuevo curso escolar.
      </td>
    </tr>
    <tr>
      <td style="padding:0.75rem;">Curso 25/26</td>
      <td style="padding:0.75rem;">Laura Agut Manrique</td>
      <td style="padding:0.75rem;">Añadidas prácticas propias.</td>
    </tr>
  </tbody>
</table>
</div>

---

## 📜 Marco normativo
El presente módulo profesional se enmarca en el 2º curso del título de Técnico Superior en Desarrollo de Aplicaciones Web. Dicho título viene regulado por:

- [Real Decreto 686/2010, de 20 de mayo](https://www.boe.es/eli/es/rd/2010/05/20/686){:target="_blank"}  
- [Real Decreto 405/2023, de 29 de mayo](https://www.boe.es/eli/es/rd/2023/05/29/405){:target="_blank"}  
- [Real Decreto 500/2024, de 21 de mayo](https://www.boe.es/eli/es/rd/2024/05/21/500){:target="_blank"}  

A nivel autonómico:  

- [ORDEN 60/2012, de 25 de septiembre](https://dogv.gva.es/es/eli/es-vc/o/2012/09/25/60/){:target="_blank"}  

---

## 📖 Licencia

<div style="border:1px solid #e5e7eb; border-radius:10px; padding:1rem; background:#f9fafb; display:flex; align-items:center; gap:1rem;">

<img src="https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png" alt="Licencia CC BY-NC-SA 4.0">

<div>
  <p>Estos apuntes derivan de la obra de <a href="https://jmunozji.github.io/DAW/">José M. Jiménez</a>, bajo licencia 
  <a href="https://creativecommons.org/licenses/by-nc-sa/4.0/">CC BY-NC-SA 4.0</a>.</p>

  <p>Modificaciones realizadas por Laura Agut en 2025: inclusión de nuevas prácticas.</p>

  <p>Esta obra mantiene la misma licencia: <b>CC BY-NC-SA 4.0</b> – Atribución · NoComercial · CompartirIgual.</p>
</div>

</div>

