# Create a basic Joule Agent using a Remote MCP Server


Create a Joule agent in Joule Studio by defining expertise and instructions to optimize the Agent's performance.

Add an remote MCP Server as "Tool" to your agent.


## Prerequisites

The agent builder is supported in the following data centers:
US30, US21, US10, JP10, EU30, EU20, EU12, EU10, AP11, AP10

You have created BTP destinations for remote MCP Servers that you want to use. For example, an entry for DeepWiki would be this:

```

#WDeepWiki.properties
Type=HTTP
Description=DeepWiki mcp
Authentication=NoAuthentication
ProxyType=Internet
URL=https\://mcp.deepwiki.com
Name=DeepWiki
sap-joule-studio-mcp-server=true
sap.processautomation.enabled=true

````

If you create it manually and not per file upload, change the URL to `https://mcp.deepwiki.com`. Don't use `/`or `/mcp` at the end of the URL.

You must set the property `sap-joule-studio-mcp-server=true`.

  
 
 <br>
 <br>
       


### Create an Agent with MCP Server


Prerequisites: You have previously created a BTP destination for DeepWiki in your Subaccount. You have added this BTP destination to your Control Tower destinations before.


1. Create a new agent, name it, for example, "WikiAgent". Go to tab "MCP Servers" and add your BTP/Build Control Tower destination for DeepWiki. 

   If the destination is correct, the Joule Agent will retrieve the available tools provided by the MCP Server.

   Click "Add Server". 

   ![alt text](images_agents/jagents_20_addmcpserver.png) 

2. Review the MCP Server.

   ![alt text](images_agents/jagents_21_mcp_deepwiki.png) 

3. Activate Joule Assistant. Enter the prompt: 

   "Create expertise and instructions for the Agent. You are an expert on GitHub, README.md files, and gitignore."

   ![alt text](images_agents/jagents_22_vibe_instructions.png)

4. Save and test the Agent.

