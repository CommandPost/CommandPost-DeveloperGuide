    <style type="text/css">
      a { text-decoration: none; }
      a:hover { text-decoration: underline; }
      th { background-color: #DDDDDD; vertical-align: top; padding: 3px; }
      td { width: 100%; background-color: #EEEEEE; vertical-align: top; padding: 3px; }
      table { width: 100% ; border: 1px solid #0; text-align: left; }
      section > table table td { width: 0; }
    </style>
    <link rel="stylesheet" href="../../css/docs.css" type="text/css" media="screen" />
    <header>
      <h1><a href="cp.battery.md">docs</a> &raquo; cp.battery</h1>
      <p>Provides access to various properties of the battery. Each of these properties
is a <code>cp.prop</code>, so it can be watched for changes. For example:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">battery</span> <span class="o">=</span> <span class="nb">require</span><span class="p">(</span><span class="s2">&quot;cp.battery&quot;</span><span class="p">)</span>
<span class="n">battery</span><span class="p">.</span><span class="n">powerSupply</span><span class="p">:</span><span class="n">watch</span><span class="p">(</span><span class="kr">function</span><span class="p">(</span><span class="n">value</span><span class="p">)</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">&quot;Now using &quot;</span><span class="o">..</span><span class="n">value</span><span class="p">)</span>
<span class="kr">end</span><span class="p">)</span>
</pre></div>
<p>This will <code>print</code> "Now using AC Power" or "Now using Battery Power" whenever the
power supply changes.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Constants - Useful values which cannot be changed</li>
          <ul>
            <li><a href="#amperage">amperage</a></li>
            <li><a href="#capacity">capacity</a></li>
            <li><a href="#cycles">cycles</a></li>
            <li><a href="#designCapacity">designCapacity</a></li>
            <li><a href="#health">health</a></li>
            <li><a href="#healthCondition">healthCondition</a></li>
            <li><a href="#isCharged">isCharged</a></li>
            <li><a href="#isCharging">isCharging</a></li>
            <li><a href="#isFinishingCharge">isFinishingCharge</a></li>
            <li><a href="#maxCapacity">maxCapacity</a></li>
            <li><a href="#otherBatteryInfo">otherBatteryInfo</a></li>
            <li><a href="#percentage">percentage</a></li>
            <li><a href="#psuSerial">psuSerial</a></li>
            <li><a href="#timeRemaining">timeRemaining</a></li>
            <li><a href="#timeToFullCharge">timeToFullCharge</a></li>
            <li><a href="#voltage">voltage</a></li>
            <li><a href="#watts">watts</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constants</h4>
          <section id="amperage">
            <a name="//apple_ref/cpp/Constant/amperage" class="dashAnchor"></a>
            <h5><a href="#amperage">amperage</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.battery.amperage &lt;cp.prop: number; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the amount of current flowing through the battery, in mAh.</p>
<p>Notes:</p>
<ul>
<li>A number containing the amount of current flowing through the battery. The value may be:
<strong> Less than zero if the battery is being discharged (i.e. the computer is running on battery power)</strong> Zero if the battery is being neither charged nor discharded
** Greater than zero if the bettery is being charged</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="capacity">
            <a name="//apple_ref/cpp/Constant/capacity" class="dashAnchor"></a>
            <h5><a href="#capacity">capacity</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.battery.capacity &lt;cp.prop: number; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the current capacity of the battery in mAh.</p>
<p>Notes:</p>
<ul>
<li>This is the measure of how charged the battery is, vs the value of <code>cp.battery.maxCapacity()</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="cycles">
            <a name="//apple_ref/cpp/Constant/cycles" class="dashAnchor"></a>
            <h5><a href="#cycles">cycles</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.battery.cycles &lt;cp.prop: number; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the number of discharge cycles of the battery.</p>
<p>Notes:</p>
<ul>
<li>One cycle is a full discharge of the battery, followed by a full charge. This may also be an aggregate of many smaller discharge-then-charge cycles (e.g. 10 iterations of discharging the battery from 100% to 90% and then charging back to 100% each time, is considered to be one cycle).</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="designCapacity">
            <a name="//apple_ref/cpp/Constant/designCapacity" class="dashAnchor"></a>
            <h5><a href="#designCapacity">designCapacity</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.battery.designCapacity &lt;cp.prop: number; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the design capacity of the battery in mAh.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="health">
            <a name="//apple_ref/cpp/Constant/health" class="dashAnchor"></a>
            <h5><a href="#health">health</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.battery.health &lt;cp.prop: string; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the health status of the battery; either "Good", "Fair" or "Poor",
as determined by the Apple Smart Battery controller.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="healthCondition">
            <a name="//apple_ref/cpp/Constant/healthCondition" class="dashAnchor"></a>
            <h5><a href="#healthCondition">healthCondition</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.battery.healthCondition &lt;cp.prop: string; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the health condition status of the battery:
<code>nil</code> if there are no health conditions to report, or a string containing either:</p>
<ul>
<li>"Check Battery"</li>
<li>"Permanent Battery Failure"</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="isCharged">
            <a name="//apple_ref/cpp/Constant/isCharged" class="dashAnchor"></a>
            <h5><a href="#isCharged">isCharged</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.battery.isCharged &lt;cp.prop: boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks if the battery is fully charged.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="isCharging">
            <a name="//apple_ref/cpp/Constant/isCharging" class="dashAnchor"></a>
            <h5><a href="#isCharging">isCharging</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.battery.isCharging &lt;cp.prop: boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks if the battery is currently charging.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="isFinishingCharge">
            <a name="//apple_ref/cpp/Constant/isFinishingCharge" class="dashAnchor"></a>
            <h5><a href="#isFinishingCharge">isFinishingCharge</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.battery.isFinishingCharge &lt;cp.prop: boolean | string; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks if the battery is trickle charging;
either <code>true</code> if trickle charging, <code>false</code> if charging faster, or `"n/a" if the battery is not charging at all.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="maxCapacity">
            <a name="//apple_ref/cpp/Constant/maxCapacity" class="dashAnchor"></a>
            <h5><a href="#maxCapacity">maxCapacity</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.battery.maxCapacity &lt;cp.prop; number; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the maximum capacity of the battery in mAh.</p>
<p>Notes:</p>
<ul>
<li>This may exceed the value of <code>cp.battery.designCapacity()</code> due to small variations in the production chemistry vs the design.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="otherBatteryInfo">
            <a name="//apple_ref/cpp/Constant/otherBatteryInfo" class="dashAnchor"></a>
            <h5><a href="#otherBatteryInfo">otherBatteryInfo</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.battery.otherBatteryInfo &lt;cp.prop: table | nil; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns information about non-PSU batteries (e.g. bluetooth accessories). If none are found, <code>nil</code> is returned.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="percentage">
            <a name="//apple_ref/cpp/Constant/percentage" class="dashAnchor"></a>
            <h5><a href="#percentage">percentage</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.battery.percentage &lt;cp.prop; string; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the current source of power; either <code>"AC Power"</code>, <code>"Battery Power"</code> or <code>"Off Line"</code>.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="psuSerial">
            <a name="//apple_ref/cpp/Constant/psuSerial" class="dashAnchor"></a>
            <h5><a href="#psuSerial">psuSerial</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.battery.psuSerial &lt;cp.prop: number; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the serial number of the attached power supply, or <code>0</code> if not present.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="timeRemaining">
            <a name="//apple_ref/cpp/Constant/timeRemaining" class="dashAnchor"></a>
            <h5><a href="#timeRemaining">timeRemaining</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.battery.timeRemaining &lt;cp.prop: number; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The amount of battery life remaining, in minuges.</p>
<p>Notes:</p>
<ul>
<li>The return value may be:
<strong> Greater than zero to indicate the number of minutes remaining.</strong> <code>-1</code> if the remaining batttery life is being calculated.
** <code>-2</code> if there is unlimited time remaining (i.e. the system is on AC power).</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="timeToFullCharge">
            <a name="//apple_ref/cpp/Constant/timeToFullCharge" class="dashAnchor"></a>
            <h5><a href="#timeToFullCharge">timeToFullCharge</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.battery.timeToFullCharge &lt;cp.prop; number; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the time remaining for the battery to be fully charged, in minutes, or `-`` if still being calculated.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="voltage">
            <a name="//apple_ref/cpp/Constant/voltage" class="dashAnchor"></a>
            <h5><a href="#voltage">voltage</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.battery.voltage &lt;cp.prop: number; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the current voltage of the battery in mV.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="watts">
            <a name="//apple_ref/cpp/Constant/watts" class="dashAnchor"></a>
            <h5><a href="#watts">watts</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.battery.watts &lt;cp.prop: number; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the power entering or leaving the battery, in W.
Discharging will be less than zero, charging greater than zero.</p>
</td>
              </tr>
            </table>
          </section>
