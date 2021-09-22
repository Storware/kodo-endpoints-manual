# Very large organization

As an example for a  very large organization \(above 2000 endpoints\) the following system configuration is recommended:

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
          <li>at least 12 cores</li>
          <li>at least 64 GB RAM</li>
          <li>at least 90 GB free disk space for operating system binaries, MySQL database
            and KODO server binaries</li>
          <li>at least 2 GB dedicated disk for /isp/db folder</li>
          <li>at least 50 GB dedicated disk for /isp/activelog folder</li>
          <li>at least 50 GB dedicated disk for /isp/archlog folder</li>
          <li>at least 50 GB dedicated disk for /isp/dbbackup folder</li>
          <li>calculations for IBM Spectrum Protect backup storage space: <b>number of endpoints </b>* <b>average amount of endpoint data to protect and the outcome divide by 2 (2:1 deduplication/compression ratio) </b>
          </li>
          <li>Network: minimum 1Gb/s connection</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

Go to the [Deployment](../../deployment/) chapter to choose your KODO for Endpoints server installation type.

