##0x034AEECB - CASP
<pre>
  DWORD version	// 0x1a is current
  DWORD offset	// to resource reference table from end of header (ie offset + 8)
</pre>
<pre>
  DWORD presetCount? // For all files I read so far, it's 0. It might still be a count
  7STRING		// UnicodeBE
  FLOAT sortPriority	// CAS sorts on this value, from largest to smallest
</pre>
<pre>
  // Unknown bytes
  // Unknown Count
  --Repeat
    DWORD flag1?
    DWORD flag2?
    Byte  Count
    --Repeat Count
      Byte TGI index reference
    Byte[] Unknown length
</pre>
<pre>
  // Resource reference table in I64GT format (not TGI64)
  BYTE count
  --repeat(count)
        QWORD instance
        DWORD group
        DWORD type
</pre>