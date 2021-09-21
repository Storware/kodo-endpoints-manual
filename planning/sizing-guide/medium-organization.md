# Medium organization

As an example for a medium organization \(up to 1000 endpoints\) the following system configuration is recommended:

<table>
  <thead>
    <tr>
      <th style="text-align:left">OS platform requirements</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <ul>
          <li>at least 6 cores</li>
          <li>at least 24 GB RAM</li>
          <li>at least 60 GB free disk space for operating system binaries, MySQL database
            and KODO server binaries</li>
          <li>at least 90 GB dedicated disk for /isp/db folder</li>
          <li>at least 420 GB dedicated disk for /isp/activelog folder</li>
          <li>at least 134 GB dedicated disk for /isp/archlog folder</li>
          <li>at least 840 GB dedicated disk for /isp/dbbackup folder</li>
          <li>Network: minimum 1Gb/s connection</li>
          <li>15 TB for IBM Spectrum Protect backup storage space (assuming 1000 endpoints
            protected with 30 GB of data on each and deduplication/compression ratio
            of 2:1)</li>
          <li>Network: minimum 1Gb/s connection</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

Now you can go over to the [Deployment](../../deployment/) chapter to choose KODO for Endpoints server installation type or go to the [Large organization](large-organization.md) chapter.

