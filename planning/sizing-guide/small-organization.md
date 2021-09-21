# Small organization

As an example for a small  organization \(up to 200 endpoints\) the following system configuration is recommended:

<table>
  <thead>
    <tr>
      <th style="text-align:left">OS platform requirement</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <ul>
          <li>at least 4 cores</li>
          <li>at least 16 GB RAM</li>
          <li>at least 50 GB free disk space for operating system binaries, MySQL database
            and KODO server binaries</li>
          <li>at least 104 GB dedicated disk for /isp/db folder</li>
          <li>at least 35 GB dedicated disk for /isp/activelog folder</li>
          <li>at least 67 GB dedicated disk for /isp/archlog folder</li>
          <li>at least 207 GB dedicated disk for /isp/dbbackup folder</li>
          <li>3 TB for IBM Spectrum Protect backup storage space (assuming 200 endpoints
            protected with 30 GB of data on each and a deduplication/compression ratio
            of 2:1)</li>
          <li>Network: minimum 1Gb/s connection</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

Now you can go over to the [Deployment](../../deployment/) chapter to choose KODO for Endpoints server installation type or go to the [Medium organization ](medium-organization.md)chapter.

