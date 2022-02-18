# OpenStack Xena
Ini adalah Contoh pembangunan infrastruktur Cloud Computing oleh OpenStack Xena. Pelajari deskripsi singkat tentang OpenStack di bawah ini sebelum membangun. (

<ul>
1) Komponen Utama OpenStack
</ul

 <table align="center" border="1" cellpadding="10">
        <tr> 
          <th>Service</th> <th>Code Name</th> <th>Description</th>
        </tr> 
        <tr>
          <td>Identity Service</td>	<td>Keystone</td>	<td>User Management</td>
        </tr>
        <tr>
          <td>Compute Service</td>	<td>Nova</td>	<td>Virtual Machine Management</td>
        </tr>
        <tr>
          <td>Image Service</td>	<td>Glance</td>	<td>Manages Virtual image like kernel image or disk image</td>
        </tr>
        <tr>
          <td>Dashboard</td>	<td>Horizon</td>	<td>Provides GUI console via Web browser</td>
        </tr>
        <tr>
            <td>DASH_DBPASS</td>
            <td>Password database untuk Dashboard</td>
        </tr>
        <tr>
            <td>DEMO_PASS</td>
            <td>Password demo pengguna</td>
        </tr>
        <tr>
            <td>GLANCE_DBPASS</td>
            <td>Password database untuk layanan Image</td>
        </tr>
         <tr>
            <td>GLANCE_PASS</td>
            <td>Password layanan Image glance pengguna</td>
        </tr> <tr>
            <td>KEYSTONE_DBPASS</td>
            <td>Password database layanan Identity</td>
        </tr> <tr>
            <td>METADATA_SECRET</td>
            <td>Rahasia untuk proxy metadata</td>
        </tr> <tr>
            <td>NEUTRON_DBPASS</td>
            <td>Password database untuk layanan Networking</td>
        </tr> <tr>
            <td>NEUTRON_PASS</td>
            <td>Password layanan Networking neutron pengguna</td>
        </tr> <tr>
            <td>NOVA_DBPASS</td>
            <td>Password database untuk layanan Compute</td>
        </tr> <tr>
            <td>NOVA_PASS</td>
            <td>Password layanan Compute nova pengguna</td>
        </tr> <tr>
            <td>PLACEMENT_PASS</td>
            <td>Sandi pengguna layanan Placement placement</td>
        </tr> <tr>
            <td>RABBIT_PASS</td>
            <td>Password dari pengguna RabbitMQ openstack</td>
 </table>
